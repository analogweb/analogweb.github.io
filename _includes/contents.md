Analogweb Framework is tiny, simple, and pluggable web framework with Scala.

This Framework helps you quickly building web API and currently supports these servers.

* Built-in non-blocking HTTP server(TLS/SSL are not supported.)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)(Strongly RECOMMENDED!)
* Servlet 2.5+ (e.g. Jetty,Tomcat,etc...) supports [servlet-plugin](https:github.com/analogweb/servlet-plugin)

First of all ,you will checkout [this project](https://github.com/analogweb/analogweb-scala-examples).

#  Quick Start

You need to add build.sbt.

{% highlight scala %}
scalaVersion := "2.12.1" 
libraryDependencies ++= Seq (
  "org.analogweb" %% "analogweb-scala" % "0.10.1-SNAPSHOT"
)
{% endhighlight %}

Start a sbt console.

{% highlight bash %}
$ sbt console
{% endhighlight %}

Write a code like this.

{% highlight scala %}
scala> import analogweb._
import analogweb._

scala> http("localhost",8000) {
    |   get("ping") { _ =>
    |     "PONG"
    |   }
    | }.run
...
INFO: An Analogweb application has been booted. (Erapsed time: 412ms)
{% endhighlight %}

Execute "sbt run" and you will get them.
    
    $ curl localhost:8000/helloworld
    $ Hello World

