Analogweb Framework Scala
===============================================
Analogweb is tiny, simple, and pluggable routing web framework.
It helps you quickly building web API and currently supports below server middleware.

- Built-in non-blocking HTTP server(TLS/SSL are not supported.)
- [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)(Strongly RECOMMENDED!)
- Servlet supports servlet-plugin (if you really want.)

## Quick Start

Create build.sbt

```scala
scalaVersion := "2.12.1" 
libraryDependencies ++= Seq (
  "org.analogweb" %% "analogweb-scala" % "0.10.1-SNAPSHOT"
)
```

Start sbt console.

```
$ sbt console
```

Write a code.

```scala
scala> import analogweb._
import analogweb._

scala> http("localhost",8000) {
    |   get("ping") { r =>
    |     "PONG"
    |   }
    | }.run
...
INFO: An Analogweb application has been booted. (Erapsed time: 412ms)
```

and you will get them.

```
$ curl localhost:8000/ping
PONG
```
