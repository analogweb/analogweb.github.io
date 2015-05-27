Analogweb Framework is tiny, simple, and pluggable web framework.

It helps you quickly building web API.

This framework running on Java and Scala.

It currently supports these servers.

* Built-in non-blocking HTTP server(TLS/SSL are not supported.)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)
* Servlet 2.5+ (e.g. Jetty,Tomcat,etc...) supports [servlet-plugin](https:github.com/analogweb/servlet-plugin)

At first ,you will checkout [helloworld](https://github.com/analogweb/helloworld)(using Java) or [helloworld-scala](https://github.com/analogweb/helloworld-scala)(using Scala) and execute run/\*.sh

#  Quick Start
You will need to install [core](https://github.com/analogweb/core) component and write them.

{% highlight java %}
package org.analogweb.hello;
    
import org.analogweb.annotation.Route;
import org.analogweb.core.Servers;

@Route("/")
public class Hello {

    public static void main(String... args) {
       Servers.run();
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
     
import org.analogweb.core.Servers
import org.analogweb.scala.Analogweb

object Hello extends Analogweb {

  def main(args: Array[String]) = Servers.run()
   
  get("/helloworld") {
     "Hello World"
  }

}
{% endhighlight %}

Run and you will get like this.
    
    $ curl http://localhost:8080/helloworld
    $ Hello World

