
  [Sbt-Launcher]: Sbt-Launcher.html
  [Compiler-Interface]: Compiler-Interface.html

## Modularization

The process we aim to take for sbt 1.0 is to disassemble sbt into smaller modules and layers.
To be clear, sbt 0.13's codebase already does consist of numerous subprojects.

Layers are more coarse-grained sets of subproject(s) that can be used independently.
Another purpose of the modularization is to distinguish between public API and internal implementation.
Reducing the surface area of the sbt code base has several benefits:

- It makes it easier for the build users and the plugin authors to learn the APIs.
- It makes it easier for us to maintain binary and semantic compatibilities.
- It encourages the reuse of the modules.

The following is a conceptual diagram of the layers:

![Module diagram](.../module-diagram.png)

This diagram is arranged such that each layer depends only on the layers underneath it.

## Module summary

### IO API (@extref[sbt/io](module:io))

IO API is a low level API to deal with files and directories.

### Serialization API (@extref[sbt/serialization](module:serialization))

Serialization API is an opinionated wrapper around @extref[Scala Pickling](github:scala/pickling). The responsibility
of the serialization API is to turn values into JSON.

### Util APIs (@extref[sbt/util](module:util))

Util APIs provide commonly used features like logging and internal datatypes used by sbt.

### LibraryManagement API (@extref[sbt/librarymanagement](module:librarymanagement))

sbt's library management system is based on Apache Ivy, and as such
the concepts and terminology around the library management system are also influenced by Ivy.
The responsibility of the library management API is to calculate the transitive dependency graph,
and download artifacts from the given repositories.

### IncrementalCompiler API (@extref[sbt/zinc](module:zinc))

Incremental compilation of Scala is so fundamental
that we now seldom think of it as a feature of sbt.
There are number of subprojects/classes involved that are actually internal details,
and we should use this opportunity to hide them.

### Build API (tbd)

This is the part that's exposed to `build.sbt`.
The responsibility of the module is to load the build files and plugins,
and provide a way for commands to be executed on the state.

This might remain at @extref[sbt/sbt](module:sbt).

### sbt Launcher (@extref[sbt/launcher](module:launcher))

The sbt launcher provides a generic container that can load and run
programs resolved using the Ivy dependency manager.
sbt uses this as the deployment mechanism, but it can be used for other purposes.

See @extref[foundweekends/conscript](github:foundweekends/conscript) and [Launcher][Sbt-Launcher] for more details.

### Client/Server (tbd)

Currently developed in @extref[sbt/sbt-remote-control](module:sbt-remote-control). sbt Server provides a JSON-based
API wrapping functionality of the command line experience.

One of the clients will be the "terminal client", which subsumes the command line sbt shell. Other clients that are
planned are IDE integrations.

### Website (@extref[sbt/website](module:website))

This website's source.
