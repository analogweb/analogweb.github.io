Analogweb Framework is tiny, simple, and pluggable web framework with Scala.

This Framework helps you quickly building web API and currently supports these servers.

* Built-in non-blocking HTTP server(TLS/SSL are not supported.)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)(Strongly RECOMMENDED!)
* Servlet 2.5+ (e.g. Jetty,Tomcat,etc...) supports [servlet-plugin](https:github.com/analogweb/servlet-plugin)

First of all ,you will checkout [this project](https://github.com/analogweb/analogweb-scala-examples).

#  Quick Start

You need to add sbt dependency to build.sbt. 

{% highlight scala %}
"org.analogweb" %% "analogweb-scala" % "0.9.14"
{% endhighlight %}

And write a code like this.

{% highlight scala %}
import org.analogweb.core.Servers
import org.analogweb.scala.Analogweb

object Hello extends Analogweb {

  def main(args: Array[String]) = Servers.run
   
  get("/helloworld") {
     "Hello World"
  }

}
{% endhighlight %}

Execute "sbt run" and you will get them.
    
    $ curl localhost:8000/helloworld
    $ Hello World

