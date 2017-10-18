  [Basic-Def]: Basic-Def.html
  [Hello]: Hello.html
  [Running]: Running.html
  [MSI]: $sbt_native_package_base$$app_version$/sbt-$app_version$.msi
  [Setup-Notes]: ../docs/Setup-Notes.html
  [Mac]: Installing-sbt-on-Mac.html
  [Windows]: Installing-sbt-on-Windows.html
  [Linux]: Installing-sbt-on-Linux.html

Installing sbt
--------------

To create an sbt project, you'll need to take these steps:

-   Install sbt.
-   Setup a simple [hello world][Hello] project
    -   Create a project directory with source files in it.
    -   Create your build definition.
-   Move on to [running][Running] to learn how to run sbt.
-   Then move on to [.sbt build definition][Basic-Def] to learn more
    about build definitions.

Ultimately, the installation of sbt boils down to a launcher JAR
and a shell script, but depending on your platform, we provide
several ways to make the process less tedious.  Head over to the
installation steps for [Mac][Mac], [Windows][Windows], or
[Linux][Linux].

### Tips and Notes

If you have any trouble running sbt, see [Setup Notes][Setup-Notes] on
terminal encodings, HTTP proxies, and JVM options.

@@@ index
* [Windows](setup/windows.md)
* [macOS](setup/macos.md)
* [Linux](setup/linux.md)
@@@
