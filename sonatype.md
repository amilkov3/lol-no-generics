
## Deploy sbt projects to Sonatype (Maven Central)

We're gonna use the following sample project tree

```
foo
- src
 - main
  - scala
core
- src
 - main
  - scala
build.sbt
```

Here's a minimal `build.sbt`

```scala
import ReleaseTransformations._

organization in ThisBuild := "your.root.package.path"

lazy val root = project.in(file("."))
  .settings(noPublishSettings: _*)
  .aggregate(foo, core)

lazy val core = project.in(file("core"))
  .settings(releasePublishSettings: _*)
  .settings(name := "mon-core")

lazy val foo = project.in(file("foo"))
  .settings(releasePublishSettings: _*)
  .settings(name := "mon-cloudwatch")
  .dependsOn(core % "compile->compile;test->test")

/** We dont want to publish the `root` module */
lazy val noPublishSettings = Seq(
  publish := (),
  publishLocal := (),
  publishArtifact := false
)

lazy val releasePublishSettings = Seq(
  releaseCrossBuild := true,
  releasePublishArtifactsAction := PgpKeys.publishSigned.value,
  releaseProcess := Seq[ReleaseStep](
    /** This is my specific list of tasks to tell the `sbt-release` plugin to run.
    You can obviously configure this differently however if you don't care particularly,
    this particular configuration works well
    */
    checkSnapshotDependencies,
    inquireVersions,
    runClean,
    runTest,
    setReleaseVersion,
    commitReleaseVersion,
    tagRelease,
    publishArtifacts,
    setNextVersion,
    commitNextVersion,
    ReleaseStep(action = Command.process("sonatypeReleaseAll", _)),
    pushChanges
  ),
  homepage := Some(url("https://github.com/yourUsername/thisProject")),
  licenses := Seq("Apache 2.0" -> url("http://www.apache.org/licenses/LICENSE-2.0")),
  publishMavenStyle := true,
  publishArtifact in Test := false,
  pomIncludeRepository := { _ => false },
  sonatypeProfileName := "ml.milkov",
  publishTo := {
    val nexus = "https://oss.sonatype.org/"
    if (isSnapshot.value)
      Some("snapshots" at nexus + "content/repositories/snapshots")
    else
      Some("releases"  at nexus + "service/local/staging/deploy/maven2")
  },
  scmInfo := Some(
    ScmInfo(
      url("https://github.com/yourUsername/thisProject"),
      "https://github.com/yourUsername/thisProject.git"
    )
  ),
  developers := List(
    Developer("yourSonatypeUsername",  "FirstName LastName", "yourEmail", url("yourWebsiteUrl"))
  )
)
```

> TIP:
> `dependsOn(core % "compile->compile;test->test")` allows you to use common test
>  code utilities defined in the `core` module in the `foo` module


You'll need the following plugins in `plugins.sbt`:

```scala
addSbtPlugin("com.dwijnand" % "sbt-travisci" % "<version>")
addSbtPlugin("org.xerial.sbt" % "sbt-sonatype" % "<version>")
addSbtPlugin("com.jsuereth" % "sbt-pgp" % "<version>")
addSbtPlugin("com.github.gseitz" % "sbt-release" % "<version>")
```





