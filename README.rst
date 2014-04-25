TODO

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
