[![Travis Build Status](https://travis-ci.org/javafx-maven-plugin/javafx-maven-plugin.svg?branch=master)](https://travis-ci.org/javafx-maven-plugin/javafx-maven-plugin)
[![AppVeyor Build status](https://ci.appveyor.com/api/projects/status/64700ul3m9y88agi/branch/master?svg=true)](https://ci.appveyor.com/project/FibreFoX/javafx-maven-plugin/branch/master)
[![Maven Central](https://img.shields.io/maven-central/v/com.zenjava/javafx-maven-plugin.svg)](https://maven-badges.herokuapp.com/maven-central/com.zenjava/javafx-maven-plugin)
[![Dependency Status](https://www.versioneye.com/java/com.zenjava:javafx-maven-plugin/8.6.0/badge.svg)](https://www.versioneye.com/java/com.zenjava:javafx-maven-plugin/8.6.0)



JavaFX Maven Plugin
===================

The JavaFX Maven Plugin provides a way to assemble distribution bundles for JavaFX applications (8+) from within Maven.
 
For easy configuration please use our new website (which needs to get updated/reworked again):
**[http://javafx-maven-plugin.github.io](http://javafx-maven-plugin.github.io)**

For (outdated) documentation/examples, your can look at archived website:
**[https://web.archive.org/web/20141009064442/http://zenjava.com/javafx/maven/](https://web.archive.org/web/20141009064442/http://zenjava.com/javafx/maven/)**



Quickstart for JavaFX JAR
=========================

Add this to your pom.xml within to your build-plugin:

```xml
<plugin>
    <groupId>com.zenjava</groupId>
    <artifactId>javafx-maven-plugin</artifactId>
    <version>8.6.0</version>
    <configuration>
        <mainClass>your.package.with.Launcher</mainClass>
    </configuration>
</plugin>
```

To create your executable file with JavaFX-magic, call `mvn jfx:jar`. The jar-file will be placed at `target/jfx/app`.



Quickstart for JavaFX native bundle
===================================

Add this to your pom.xml within to your build-plugin:

```xml
<plugin>
    <groupId>com.zenjava</groupId>
    <artifactId>javafx-maven-plugin</artifactId>
    <version>8.6.0</version>
    <configuration>
        <vendor>YourCompany</vendor>
        <mainClass>your.package.with.Launcher</mainClass>
    </configuration>
</plugin>
```

To create your executable file with JavaFX-magic and some installers (please see official oracle-documentation which applications are required for this), call `mvn jfx:native`. The native launchers or installers will be placed at `target/jfx/native`.



Prepared for Java 9
===================

Add repository in your `pom.xml` for snapshot-versions of this plugin:

```xml
<pluginRepositories>
    <pluginRepository>
        <id>oss-sonatype-snapshots</id>
        <url>https://oss.sonatype.org/content/groups/public/</url>
        <snapshots>
            <enabled>true</enabled>
        </snapshots>
    </pluginRepository>
</pluginRepositories>
```

Set version to new SNAPSHOT-version:

```xml
<plugin>
    <groupId>com.zenjava</groupId>
    <artifactId>javafx-maven-plugin</artifactId>
    <version>9.0.0-SNAPSHOT</version>
    <configuration>
        <!-- your configuration -->
    </configuration>
</plugin>
```

*Some notes: as this isn't the main branch, a lot of features aren't present in that branch yet, deployment of new "-SNAPSHOT"-version are on-demand*
**This is currently heavily outdated**



Last Release Notes
==================

**Version 8.6.0 (01-Sept-2016)**

New:
* added new property `useEnvironmentRelativeExecutables` to make sure having the correct executables used, required when having multiple installations of java, just set this to false for using the JDK used for executing maven  (this got migrated from the [javafx-gradle-plugin](https://github.com/FibreFoX/javafx-gradle-plugin))
* added new property `runAppParameter` for specifying application parameters passed to the execution call `java -jar` while developing your application (this fixes #176, because that issue got valid as the `mvn jfx:run` goal is valid again after the removal of the `exec-maven-plugin`)
* added new property `runJavaParameter` for having additional settings passed to the execution call used for running your javafx-application, makes it possible to specify javassist-parameters now (and much more)

Bugfixes:
* fixed tests not running on MacOSX due to different paths exceptations (thanks @sa-wilson)

Improvements:
* cleanup of some unused parameters
* fixed missing "s" inside description about `jfx:list-bundlers`-mojo



(Not yet) Release(d) Notes
==========================

upcoming Version 8.6.1 (???-2016)

* nothing changed yet