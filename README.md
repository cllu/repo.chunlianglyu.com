# My Maven Repository

## Setup a sbt project

Suppose the repo is checkout at `~/Project/repo.chunlianglyu.com`, add the following line to the Build.scala file:

    publishTo := Some(Resolver.file("file",  new File(Path.userHome.absolutePath+"/Projects/repo.chunlianglyu.com"))),

Then run `sbt publish` to publish the library to this directory.

To use the libraries in this repo, add the resolver:

    resolvers += "Chunliang's Maven Repository" at "https://repo.chunlianglyu.com"
    libraryDependencies += "com.chunlianglyu.sorm2" %% "sorm2" % "0.4.0"

