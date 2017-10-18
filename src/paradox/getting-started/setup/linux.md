---
title: Linux
---

  [ZIP]: $sbt_native_package_base$$app_version$/sbt-$app_version$.zip
  [TGZ]: $sbt_native_package_base$$app_version$/sbt-$app_version$.tgz
  [RPM]: $sbt_rpm_package_base$sbt-$app_version$.rpm
  [DEB]: $sbt_deb_package_base$sbt-$app_version$.deb
  [Manual-Installation]: Manual-Installation.html
  [website127]: https://github.com/sbt/website/issues/127

## Linux Setup

### Installing from a universal package

Download [ZIP][ZIP] or [TGZ][TGZ] package and expand it.

### Ubuntu and other Debian-based distributions

[DEB][DEB] package is officially supported by sbt.

Ubuntu and other Debian-based distributions use the DEB format, but usually you don't install your software from a local
DEB file. Instead they come with package managers both for the command line (e.g. `apt-get`, `aptitude`) or with a
graphical user interface (e.g. Synaptic).

Run the following from the terminal to install `sbt` (You'll need superuser privileges to do so, hence the `sudo`).

```shell
echo "deb https://dl.bintray.com/sbt/debian /" | sudo tee -a /etc/apt/sources.list.d/sbt.list
sudo apt-key adv --keyserver hkp://keyserver.ubuntu.com:80 --recv 2EE0EA64E40A89B84B2DF73499E82A75642AC823
sudo apt-get update
sudo apt-get install sbt
```

Package managers will check a number of configured repositories for packages to offer for installation. sbt binaries are
published to Bintray, and conveniently Bintray provides an APT repository. You just have to add the repository to the
places your package manager will check.

Once `sbt` is installed, you'll be able to manage the package in `aptitude` or Synaptic after you updated their package
cache. You should also be able to see the added repository at the bottom of the list in
System Settings → Software & Updates → Other Software:

![Ubuntu Software & Updates Screenshot](files/ubuntu-sources.png "Ubuntu Software & Updates Screenshot")

### Red Hat Enterprise Linux and other RPM-based distributions

[RPM][RPM] package is officially supported by sbt.

Red Hat Enterprise Linux and other RPM-based distributions use the RPM format.
Run the following from the terminal to install `sbt` (You'll need superuser privileges to do so, hence the `sudo`).

```shell
curl https://bintray.com/sbt/rpm/rpm | sudo tee /etc/yum.repos.d/bintray-sbt-rpm.repo
sudo yum install sbt
```

sbt binaries are published to Bintray, and conveniently Bintray provides an RPM repository. You just have to add the repository to the places your package manager will check.

@@@ note
Please report any issues with these to the [sbt-launcher-package](https://github.com/sbt/sbt-launcher-package) project.
@@@

### Gentoo

The official tree contains ebuilds for sbt. To install the latest available version do:

```shell
emerge dev-java/sbt
```
