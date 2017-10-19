
  [Getting-Started]: getting-started/index.md
  [Setup]: getting-started/setup.md
  [Basic-Def]: Basic-Def.html
  [Library-Dependencies]: Library-Dependencies.html
  [Multi-Project]: Multi-Project.html
  [Name-Index]: Name-Index.html
  [Triggered-Execution]: Triggered-Execution.html
  [Java-Sources]: Java-Sources.html
  [Testing]: Testing.html
  [Parallel-Execution]: Parallel-Execution.html

# sbt Reference Manual

sbt is a build tool for Scala, Java, and [more](https://github.com/d40cht/sbt-cpp). It requires Java 1.8 or later.

### Install

See @ref:[Installing sbt][Setup] for the setup instructions.

### Getting Started

To get started, *please read* the @ref:[Getting Started Guide][Getting-Started]. You will save yourself a *lot* of time
if you have the right understanding of the big picture up-front.

Use [Stack Overflow](https://stackoverflow.com/tags/sbt) for questions. Use the
[sbt-dev mailing list](https://groups.google.com/d/forum/sbt-dev) for discussing sbt development. Use
[@scala_sbt](https://twitter.com/scala_sbt) for questions and discussions.

### Features of sbt

* Little or no configuration required for simple projects.
* Scala-based [build definition][Basic-Def] that can use the full flexibility of Scala code.
* Accurate incremental recompilation using information extracted from the compiler.
* Continuous compilation and testing with [triggered execution][Triggered-Execution].
* Packages and publishes jars
* Generates documentation with scaladoc
* Supports mixed Scala/[Java][Java-Sources] projects
* Supports [testing][Testing] with ScalaCheck, specs, and ScalaTest. JUnit is supported by a plugin.
* Starts the Scala REPL with project classes and dependencies on the classpath
* Modularization supported with [sub-projects][Multi-Project]
* External project support (list a git repository as a dependency!)
* [Parallel task execution][Parallel-Execution], including parallel test execution
* [Library management support][Library-Dependencies]: inline declarations, external Ivy or Maven configuration files,
    or manual management

### Also

This documentation can be forked on [GitHub](https://github.com/sbt/website/). Feel free to make corrections and add
documentation.

Documentation for 0.7.x has been [archived here](http://www.scala-sbt.org/0.7.7/docs/home.html). This documentation
applies to sbt $app_version$.

See also the [API Documentation](../api/index.html), and the [index of names and types][Name-Index].

@@@ index
* [Getting Started](getting-started/index.md)
* [Plugin Devleopers](plugin-developers/index.md)
* [sbt Developers](developing-sbt/index.md)
* [FAQ](faq.md)
@@@
