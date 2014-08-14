jmh-profilers
=============

Profilers for JMH that are passed through SPI.

Test by passing the ```-lprof``` option to discover ```ExternalProfiler```s.

```
java -cp ./jmh-profilers.jar -jar build/java/microbenchmarks.jar -lprof
```
