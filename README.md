Oppressor API for Scala.js
================================
This is a Scala.js type-safe binding for [Oppressor](https://www.npmjs.com/package/oppressor)

A streaming http compression response negotiator.
 

#### Build Dependencies

* [ScalaJs.io v0.3.x](https://github.com/ldaniels528/scalajs.io)
* [SBT v0.13.13](http://www.scala-sbt.org/download.html)

#### Build/publish the SDK locally

```bash
 $ sbt clean publish-local
```

#### Running the tests

Before running the tests the first time, you must ensure the npm packages are installed:

```bash
$ npm install
```

Then you can run the tests:

```bash
$ sbt test
```

#### Examples

```scala
  val server = Http.createServer((req: ClientRequest, res: ServerResponse) => {
    Fs.createReadStream("./npm/csv-parse/src/test/resources/data.txt")
      .pipe(Oppressor(req))
      .pipe(res)
  })
  server.listen(8000)
```

#### Artifacts and Resolvers

To add the Moment binding to your project, add the following to your build.sbt:  

```sbt
libraryDependencies += "io.scalajs.npm" %%% "oppressor" % "0.3.0.3"
```

Optionally, you may add the Sonatype Repository resolver:

```sbt   
resolvers += Resolver.sonatypeRepo("releases") 
```