[![Build Status](https://travis-ci.org/analogweb/analogweb-scala.svg)](https://travis-ci.org/analogweb/analogweb-scala)
[![codecov](https://codecov.io/gh/analogweb/analogweb-scala/branch/master/graph/badge.svg)](https://codecov.io/gh/analogweb/analogweb-scala)
[![Codacy Badge](https://api.codacy.com/project/badge/Grade/7a112498f9ae4e3d996a8a74d59a1c4e)](https://www.codacy.com/manual/y2k2mt/analogweb-scala?utm_source=github.com&amp;utm_medium=referral&amp;utm_content=analogweb/analogweb-scala&amp;utm_campaign=Badge_Grade)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/org.analogweb/analogweb-scala_2.13/badge.svg)](https://maven-badges.herokuapp.com/maven-central/org.analogweb/analogweb-scala_2.13)
[![License](http://img.shields.io/:license-mit-blue.svg)](http://doge.mit-license.org)
[![FOSSA Status](https://app.fossa.io/api/projects/git%2Bgithub.com%2Fanalogweb%2Fanalogweb-scala.svg?type=shield)](https://app.fossa.io/projects/git%2Bgithub.com%2Fanalogweb%2Fanalogweb-scala?ref=badge_shield)

Analogweb Framework is tiny, simple, and pluggable web framework with Scala.

This Framework helps you quickly building web API and currently supports these servers.

* Built-in non-blocking HTTP server(TLS/SSL are not supported.)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)(Strongly RECOMMENDED!)
* Servlet 2.5+ (e.g. Jetty,Tomcat,etc...) supports [servlet-plugin](https:github.com/analogweb/servlet-plugin)

#  Quick Start

You need to add sbt dependency on build.sbt. 

{% highlight scala %}
scalaVersion := "2.13.1"
libraryDependencies ++= Seq (
  "org.analogweb" %% "analogweb-scala" % "0.12.0"
)
{% endhighlight %}

And write a few lines of code.

{% highlight scala %}
import analogweb._

http("localhost",8000) {
  get("/helloworld") { "Hello, World" }
}.run
{% endhighlight %}

Execute `sbt run` and you will get them.
    
{% highlight bash %}
$ curl localhost:8000/helloworld
$ Hello World
{% endhighlight %}

# Examples

More examples, please watch [this project](https://github.com/analogweb/analogweb-scala-examples).
