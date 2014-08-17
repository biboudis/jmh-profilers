JMH Pluggable Profilers
=======================

Pluggable profilers for [JMH](http://openjdk.java.net/projects/code-tools/jmh/) that are discovered through SPI (for [JMH >= 0.9.7](http://mail.openjdk.java.net/pipermail/jmh-dev/2014-August/001280.html)).

Profilers List
--------------
* [jfr](https://github.com/biboudis/jmh-profilers/blob/master/src/main/java/profilers/FlightRecordingProfiler.java): starts automatically [Java Flight Recorder](http://docs.oracle.com/javase/8/docs/technotes/guides/jfr/) 
and produces a .jfr file for each benchmark. Each file can be browsed afterwards via [Java Mission Control](http://www.oracle.com/technetwork/java/javaseproducts/mission-control/java-mission-control-1998576.html).
This profiler can be considered by JMH as ```supported``` only if the user wants to explicitly enable the [commercial features](http://www.oracle.com/technetwork/java/javase/terms/products/index.html).

Test
----
```
java -Djava.ext.dirs=../jmh-profilers/out/artifacts/jmh_profilers/:build/java/ -cp microbenchmarks.jar:jmh-profilers.jar org.openjdk.jmh.Main -lprof
```

This would append in the list of supported or unsupported profilers an entry of the following format:

```
<label>: <description>. (discovered)
```

The jmh patch
-------------
[This patch](http://mail.openjdk.java.net/pipermail/jmh-dev/2014-August/001274.html) 
enables SPI-based discovery of profilers in JMH. 
Test by passing the ```-lprof``` option to discover ```Profiler```s. They should be marked with the (discovered) label under the supported or unsupported list.



