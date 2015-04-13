## JMH Pluggable Profilers
[![Build Status](https://travis-ci.org/biboudis/jmh-profilers.svg?branch=master)](https://travis-ci.org/biboudis/jmh-profilers)

Pluggable profilers for [JMH](http://openjdk.java.net/projects/code-tools/jmh/)
that are discovered through SPI (for JMH >= 1.8) when the profiler is present in the classpath.

### Profilers List
1. JFR Profiler: starts automatically [Java Flight Recorder](http://docs.oracle.com/javase/8/docs/technotes/guides/jfr/)
and produces a .jfr file for each benchmark. Each file can be browsed afterwards
via
[Java Mission Control](http://www.oracle.com/technetwork/java/javaseproducts/mission-control/java-mission-control-1998576.html).
This profiler can be considered by JMH as ```supported``` only if the user wants
to explicitly enable the
[commercial features](http://www.oracle.com/technetwork/java/javase/terms/products/index.html).

### Installation 
#### Maven
```
<dependency>
  <groupId>com.github.biboudis</groupId>
  <artifactId>jmh-profilers</artifactId>
  <version>0.1.2</version>
</dependency>
```
#### SBT with sbt-jmh plugin
```
libraryDependencies ++= Seq("com.github.biboudis" % "jmh-profilers" % "0.1.2")
```

### Usage
Check if your profiler is discovered through the ```-lprof``` JMH option. This
would append in the list of supported or unsupported profilers an entry of the
following format:
```
<label>: <description>. (discovered)
```

### Contributing

Sending PRs with improvements, additions with new profilers and opening issues is highly encouraged. 
