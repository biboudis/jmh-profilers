jmh-profilers
=============

Profilers for JMH that are passed through SPI.

Test by passing the ```-lprof``` option to discover ```ExternalProfiler```s.

```
java -Djava.ext.dirs=../jmh-profilers/out/artifacts/jmh_profilers/:build/java/ -cp microbenchmarks.jar:jmh-profilers.jar org.openjdk.jmh.Main -lprof -v EXTRA
```