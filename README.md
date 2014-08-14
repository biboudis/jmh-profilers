jmh-profilers
=============

Profilers for JMH that are passed through SPI.

Assuming the directory structure by passing the ```-lprof``` the discovered ```ExternalProfiler```s are discovered.

java -cp ~/Projects/jmh-profilers/out/artifacts/jmh_profilers/jmh-profilers.jar -jar build/java/microbenchmarks.jar -lprof
