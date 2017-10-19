## Cross-building Plugins

Like we are able to cross build against multiple Scala versions, we can cross-build sbt 1.0 plugins while staying on
sbt 0.13 (and build 0.13 plugins from 1.0). This is useful because we can port one plugin at a time.

### Enabling cross-building

sbt 0.13.16 added a new `crossSbtVersions` setting, which acts in a similar way to `crossScalaVersions`, and two new
commands (`^` and `^^`) to switch the target sbt version.


```scala
crossSbtVersions := Seq("0.13.16", "1.0.2")
```

We can now target sbt 1.0.2 using:

```
> ^^1.0.2
[info] Setting `sbtVersion in pluginCrossBuild` to 1.0.2
```

Tasks can also be run against all cross-build sbt versions using `^^`:

```
> ^compile
[info] Setting `sbtVersion in pluginCrossBuild` to 0.13.16
[info] Compiling 25 Scala sources to /home/sbt/example-plugin/target/scala-2.10/sbt-0.13/classes ...
...
[info] Setting `sbtVersion in pluginCrossBuild` to 1.0.2
[info] Compiling 25 Scala sources to /home/sbt/example-plugin/target/scala-2.12/sbt-1.0/classes ...
```

### Version specific code

While most APIs are the same in sbt 0.13 and 1.0 there are some changes require differing code paths. When building a
cross-build plugin, sbt provides additional Scala source directories specific to the target sbt version:

```
src/main/scala
src/main/scala-sbt-0.13
src/main/scala-sbt-1.0
```

When compiling for sbt 1.0 the `src/main/scala` and `src/main/scala-sbt-1.0` directories will be used (and conversely
for sbt 0.13 `src/main/scala-sbt-0.13` will be used).

@@@ note
You should aim to keep the amount of sbt version specific code to a minimum.
@@@

### sbt-compat

[sbt-compat](https://github.com/dwijnand/sbt-compat) is a compatibility layer that aims to plug the gap in APIs between
sbt 0.13 and sbt 1.0. Adding this plugin to your cross-build plugin will allow you to use some of the new sbt 1.0 APIs
when building for sbt 0.13.
