Analogweb Framework
===================

Analogweb is tiny, simple, and pluggable routing web framework.
It helps you quickly building web API.

This framework running on Java and Scala.(if JVM it can run on anyware.)
It currently supports below middleware.

* [Sun HttpServer](docs.oracle.com/javase/7/docs/jre/api/net/httpserver/spec/com/sun/net/httpserver/package-summary.html)
* [Netty4](http://netty.io) supports [netty-plugin](https://github.com/analogweb/netty-plugin)
* Servlet supports servlet-plugin (if you really want.)

At first ,you will checkout helloworld and execute run/\*.sh

#  Quick Start
You will need to install [analogweb-core](https://github.com/analogweb/core) component and write below.

'''java
package org.analogweb.hello;

import org.analogweb.annotation.Route;
import org.analogweb.core.httpserver.HttpServers;

@Route("/")
public class Hello {

      public static void main(String... args) {
         HttpServers.create("http://localhost:8080").start();
      }

      @Route
      public String hello() {
         return "Hello World";
      }

}
'''
And then install [scala-plugin](https://github.com/analogweb/scala-plugin) and write below.

'''scala

import org.analogweb.core.httpserver.HttpServers
import org.analogweb.scala.Analogweb

object Run {
    def main(args: Array[String]): Unit = {
       HttpServers.create("http://localhost:8080").start()
    }
}

class Hello extends Analogweb {
    def hello = get("/hello") { request => 
       "Hello World"
    }
}
'''

