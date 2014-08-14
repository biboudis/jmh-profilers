jmh-profilers
=============

Profilers for JMH that are passed through SPI.

Test by passing the ```-lprof``` option to discover ```ExternalProfiler```s.

```
java -cp ./jmh-profilers.jar -jar build/java/microbenchmarks.jar -lprof
```

(or [according to the classpath not passed when -jar](http://stackoverflow.com/questions/945962/java-problem-running-a-jar-file-in-command-line))

```
java -cp build/java/microbenchmarks.jar:../jmh-profilers/out/artifacts/jmh_profilers/jmh-profilers.jar org.openjdk.jmh.Main -lprof
```