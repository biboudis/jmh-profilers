jmh-profilers
=============

Profilers for [JMH](http://openjdk.java.net/projects/code-tools/jmh/) that are discovered through SPI.

Profilers List
--------------
* jfr: The profiler that starts automatically [Java Flight Recording](http://docs.oracle.com/javase/8/docs/technotes/guides/jfr/) 
and produces a .jfr file for each benchmark. Each file can be browsed afterwards via [Java Mission Control](http://www.oracle.com/technetwork/java/javaseproducts/mission-control/java-mission-control-1998576.html).
This profiler can be considered supported only if the user wants to explicitly enable the [commercial features](http://www.oracle.com/technetwork/java/javase/terms/products/index.html).

The jmh patch
-------------
[The patch included in this repository](https://github.com/biboudis/jmh-profilers/blob/master/cr/Lightweight_external_profiler_discovery_through_SPI_.patch) enables SPI-based discovery of profilers in JMH. Test by passing the ```-lprof``` option to discover ```ExternalProfiler```s.

```
java -Djava.ext.dirs=../jmh-profilers/out/artifacts/jmh_profilers/:build/java/ -cp microbenchmarks.jar:jmh-profilers.jar org.openjdk.jmh.Main -lprof
```

This would append in the list of supported or unsupported profilers an entry of the following format:

```
<label>: <description>. (discovered)
```

The "(discovered)" flag was added, as a discovered profiler can be a not-supported one as well. So in order to avoid duplication this indication is included. 


