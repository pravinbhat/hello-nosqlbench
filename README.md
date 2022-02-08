# Helpful links
* [NoSQLBench Docs](https://docs.nosqlbench.io/)
* [CQLSH for Astra](https://downloads.datastax.com/#cqlsh)
* [Cassandra cluster manager (CCM)](https://github.com/riptano/ccm)

# Why performance testing: 
* Never take workloads live w/o stress testing
* Baselines benchmarks and measure trends as new features are deployed 
* Performance testing with Cassandra:
 - Take it a step further: Test your model before active development
 - Helps avoid painful refactoring & scaling issues 
 - Know your access patterns (queries & data) up front

# Why/What NoSQL Bench?
* Virtual Datasets
 - Deterministic 
 - Dynamically generated at runtime
 - Flexible & ​customizable workloads using plain `YAML`
 - Statistically shaped (many options to generate load that mimics your app)
* Command-line based: Linux binary or JAR executable 
 - JAR option needs `JRE 11+` (preferably `JRE 17+`)
* Scale is difficult to estimate, sometimes a good data-model on paper may not scale in practice. Always verify using a stress testing tool.
 - NoSQLBench is a powerful tool for serious (yet simple) stress testing

# Workloads
* Created using Blocks, Statements, Cycles, Tags, Bindings, Params
* Bindings: Key to use NoSQLBench effectively
 - Doc for [binding functions](https://docs.nosqlbench.io/docs/bindings/binding-concepts/)
* Test workloads using `STDOUT` driver & when execute in Cassandra using `CQL` driver

# Run workloads 
```
java -jar nb.jar start driver=stdout workload=/<path-to-workload-file>/ratios cycles=21
java -jar nb.jar start driver=cql workload=/<path-to-workload-file>/products tags=phase:schema
java -jar nb.jar start driver=cql workload=/<path-to-workload-file>/products tags=phase:main cycles=10
```
