# hekwagter
Distributed server for issuing identification keys (IDs) with configurable ID formats by the clients

### Specifications (work in progress)
 1. Generating IDs based on clients configuration scheme. 
 2. Binary protocol over TCP connection.
 3. Multithreaded & distributed server.
 4. Ability to generate snowflake like IDs with customizable scheme and custom epoch.
 5. Avoiding [Poisson Distribution](http://en.wikipedia.org/wiki/Poisson_distribution) for random ID generation.
 6. Monitor system clock and refuse to generate IDs (with time component) if clock moves backward.
 7. Provide IDs generation as a library and as a service over TCP/IP.
 
### Issues
 1. [Clock skew/drift](http://www.wikiwand.com/en/Clock_skew) is a problem in distributed systems.
 2. IDs of `flake` type are not exactly time sorted.
 3. Generating sequential IDs requires a coordination with `bookkeeper` service for acquiring ID ranges.
 
