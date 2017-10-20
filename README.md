# abc4j (fork)

[![Build Status](https://travis-ci.org/Sciss/abc4j.svg?branch=master)](https://travis-ci.org/Sciss/abc4j)
[![Maven Central](https://maven-badges.herokuapp.com/maven-central/de.sciss/abc4j/badge.svg)](https://maven-badges.herokuapp.com/maven-central/de.sciss/abc4j)

## statement

This is a fork of the [abc4j](https://code.google.com/p/abc4j/) library. The code was originally written by Lionel Guéganton (2006–2008), continued by pipemakertjm (2009) and Sylvain Machefert (iubito) (2009–2011). This library is published under the [GNU Lesser General Public License (LGPL) v3+](https://raw.github.com/Sciss/abc4j/master/LICENSE). All modifications (C)opyright 2013&ndash;2016 by Hanns Holger Rutz, released by that same license. Modified source files are marked in the header. The kind of modifications, file removals etc., are documented by way of the git history.

Why a fork? (a) I needed to get an easy handle on the source. (b) I am planning to strip this down to a plain score display component. (c) Github instead of Google-Code. (d) Building with sbt. (e) Publishing (eventually) to Maven Central, making it available for automatic dependency management.

To contact Hanns Holger Rutz, send a mail to `contact@sciss.de`.

## linking

Use the following artifact. Maven syntax:

    <dependency>
      <groupId>de.sciss</groupId>
      <artifactId>abc4j</artifactId>
      <version>0.6.0</version>
    </dependency>

sbt syntax:

    "de.sciss" % "abc4j" % "0.6.+"

## building and running

A build file for [sbt](http://www.scala-sbt.org/) version 0.13 is provided. If you have never used sbt, either follow the instructions on the sbt website for installation, or use (recommended) the [sbt-extras](https://github.com/paulp/sbt-extras) shell script. On OS X or Linux, this should be as simple as running the following line from a terminal:

    curl -s https://raw.github.com/paulp/sbt-extras/master/sbt > ~/bin/sbt && chmod 0755 ~/bin/sbt

It assumes you have directory `~/bin` and it is on your `PATH` (i.e., added to `~/.bash_profile`).

After you have installed sbt, compiling is as simple as running `sbt test:compile`. To run the unit tests, use `sbt test`. To run the main demo, use `sbt abc4j/run`. This creates images files `abc4j_demoJustified.jpg` and `abc4j_demoNotjustified.jpg` in your home or desktop folder. To run the Acynth application, use `sbt abc4j-abcynth/run`. Here you may want to open the file `src/main/resources/abcynth/LGtunes.abc`.

To generate the javadoc API: `sbt abc4j/doc`.

There are currently 8 tests failing in these classes:

    [error] Failed tests:
    [error] 	TuneBookTest
    [error] 	SlursTest
    [error] 	TieTest
    [error] 	GracingsTest

This still has to be investigated...

## contributing

Please see the file [CONTRIBUTING.md](CONTRIBUTING.md)

## applets

There there are two html files in the `applets` folder which embed abc4j as Java applets. They require that a compound jar has been created in the `target` folder using `sbt assembly`. `checkApplet.html` simply allows to enter an abc notated text and runs the parser to see if is valid code. `abcynthApplet.html` runs the tune book application. You might need to run it twice due to some null exceptions in configuration.

## overview

Please refer to the [original website](https://code.google.com/p/abc4j/) for documentation.
