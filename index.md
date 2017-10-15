---
# You don't need to edit this file, it's empty on purpose.
# Edit theme's home layout instead if you wanna make some changes
# See: https://jekyllrb.com/docs/themes/#overriding-theme-defaults
layout: default
---
Analogweb is tiny, simple, and pluggable web framework for Scala.

This framework helps you quickly building web API and currently supports these servers.

* Built-in non-blocking HTTP server(TLS/SSL are not supported.)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)(Strongly RECOMMENDED!)
* Servlet 2.5+ (e.g. Jetty,Tomcat,etc...) supports [servlet-plugin](https:github.com/analogweb/servlet-plugin)

First of all ,you will checkout [this project](https://github.com/analogweb/analogweb-scala-examples).

#  Quick Start

Let's create ``` build.sbt ```.

{% highlight scala %}
scalaVersion := "2.12.1" 
libraryDependencies ++= Seq (
  "org.analogweb" %% "analogweb-scala" % "0.10.1"
)
{% endhighlight %}

Start a sbt console.

{% highlight bash %}
$ sbt console
{% endhighlight %}

Write a code like below.

{% highlight scala %}
scala> import analogweb._
import analogweb._

scala> http {
    |   get("plaintext") { _ =>
    |     "Hello, World!"
    |   }
    | }.run
...
INFO: An Analogweb application has been booted. (Erapsed time: 412ms)
{% endhighlight %}

... and you will get them.

{% highlight bash %}
$ curl localhost:8000/plaintext
$ Hello, World!
{% endhighlight %}
