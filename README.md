# My Maven Repository

## Packages

- `"com.chunlianglyu.bliki2" % "bliki2" % "3.2.0"`
- `"com.chunlianglyu.sorm2" % "sorm2" %% "0.4.2"`
- `"org.nlpcn" % "nlp-lang" % "1.0.2"`
- `"org.ansj" % "ansj_seg" % "2.0.8"`

## Setup a sbt project

Suppose the repo is checkout at `~/Projects/repo.chunlianglyu.com`, add the following line to the Build.scala file:

    publishTo := Some(Resolver.file("file",  new File(Path.userHome.absolutePath+"/Projects/repo.chunlianglyu.com"))),

Then run `sbt publish` to publish the library to this directory.

To use the libraries in this repo, add the resolver:

    resolvers += "Chunliang's Maven Repository" at "https://repo.chunlianglyu.com"
    libraryDependencies += "com.chunlianglyu.sorm2" %% "sorm2" % "0.4.1"
    libraryDependencies += "com.chunlianglyu.bliki2" %% "bliki2" % "3.2.0"

## Setup a maven project

Add the following configurations to `pom.xml`:

```xml
<distributionManagement>
  <repository>
    <id>com.chunlianglyu.bliki2</id>
    <url>file:/Users/cllu/Projects/repo.chunlianglyu.com/</url>
  </repository>
</distributionManagement>
```

And then run `mvn deploy` to publish to the directory.
