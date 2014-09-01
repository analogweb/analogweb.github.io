Analogweb is tiny, simple, and pluggable web framework.

It helps you quickly building web API.

This framework running on Java and Scala.

It currently supports below servers.

* [Sun HttpServer](http://docs.oracle.com/javase/7/docs/jre/api/net/httpserver/spec/com/sun/net/httpserver/package-summary.html)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)
* Servlet(e.g. Jetty,Tomcat,etc...) supports [servlet-plugin](https:github.com/analogweb/servlet-plugin) (if you really want.)

At first ,you will checkout [helloworld](https://github.com/analogweb/helloworld) and execute run/\*.sh

#  Quick Start
You will need to install [analogweb-core](https://github.com/analogweb/core) component and write them.

    package org.analogweb.hello;
    
    import org.analogweb.annotation.Route;
    import org.analogweb.core.httpserver.HttpServers;

    @Route("/")
    public class Hello {

        public static void main(String... args) {
           HttpServers.create("http://localhost:9060").start();
        }

        @Route
        public String hello() {
           return "Hello World";
        }

    }

Otherwise, install [scala-plugin](https://github.com/analogweb/scala-plugin) and write them.

    import org.analogweb.core.httpserver.HttpServers
    import org.analogweb.scala.Analogweb

    object Run {
       def main(args: Array[String]): Unit = {
          HttpServers.create("http://localhost:9060").start()
       }
    }
    
    class Hello extends Analogweb {
       def hello = get("/hello") { request => 
          "Hello World"
       }
    }

And then You will get
    
    $ curl http://localhost:9060/hello
    $ Hello World
