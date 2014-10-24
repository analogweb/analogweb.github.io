Analogweb Framework is tiny, simple, and pluggable web framework.

It helps you quickly building web API.

This framework running on Java and Scala.

It currently supports these servers.

* [Sun HttpServer](http://docs.oracle.com/javase/7/docs/jre/api/net/httpserver/spec/com/sun/net/httpserver/package-summary.html)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)
* Servlet(e.g. Jetty,Tomcat,etc...) supports [servlet-plugin](https:github.com/analogweb/servlet-plugin) (if you really want.)

At first ,you will checkout [helloworld](https://github.com/analogweb/helloworld)(using Java) or [helloworld-scala](https://github.com/analogweb/helloworld-scala)(using Scala) and execute run/\*.sh

#  Quick Start
You will need to install [core](https://github.com/analogweb/core) component and write them.

{% highlight java %}
package org.analogweb.hello;
    
import org.analogweb.annotation.Route;
import org.analogweb.core.httpserver.HttpServers;

@Route("/")
public class Hello {

    public static void main(String... args) {
       HttpServers.create("http://localhost:8080").start();
    }

    @Route
    public String helloworld() {
       return "Hello World";
    }

}
{% endhighlight %}

Otherwise, you also install [scala-plugin](https://github.com/analogweb/scala-plugin) and write them.

{% highlight scala %}
package org.analogweb.hello
     
import org.analogweb.core.httpserver.HttpServers
import org.analogweb.scala.Analogweb

object Run {
   def main(args: Array[String]): Unit = {
      HttpServers.create("http://localhost:8080").start()
   }
}
    
class Hello extends Analogweb {
   def hello = get("/helloworld") { request => 
      "Hello World"
   }
}
{% endhighlight %}

Run and you will get like this.
    
    $ curl http://localhost:8080/helloworld
    $ Hello World

