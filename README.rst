Note
----

https://github.com/scala/scala-continuations

  You may also be interested in https://github.com/scala/async, which covers
  the most common use case for the continuations plugin.

  The Scala Delimited Continuations Plugin and Library will continue to ship
  with Scala 2.11.0. However, it will no longer be included with Scala 2.12.

Add xitrum-imperatively
-----------------------

Add to build.sbt of your Xitrum 3.8+ project:

::

  // xitrum-imperatively uses Scala continuation, a compiler plugin --------------

  libraryDependencies += "tv.cntt" %% "xitrum-imperatively" % "1.0"

  autoCompilerPlugins := true

  // https://groups.google.com/forum/?fromgroups#!topic/simple-build-tool/ReZvT14noxU
  libraryDependencies <+= scalaVersion { sv =>
    compilerPlugin("org.scala-lang.plugins" % s"scala-continuations-plugin_$sv" % "1.0.1")
  }

  scalacOptions += "-P:continuations:enable"

Usage
-----

TODO
