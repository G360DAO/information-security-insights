# Generic information security insight requirements

## Documentation

### Information about the author

* (nick)Name
* Wallet address
* Emailaddress

### Information about the security insight application

* Security insight purpose (description)
* Elaborate on the output of the security insight application
* Step-by-step guide how to run the security insight application
* Step-by-step guide how to reproduce and verify results manually

### Licensing

* Statement that MIT License applies

## Technical requirements

### Security insight application build

* Dockerfile + docker-compose.yml
* Scalable and able to run automated
  * Docker scratch image (FROM scratch) with a single binary (symbols stripped, upx compressed)
  * Read-only file system, no data should be written to disk, no temp files, all processed in-memory
  * Run non-privileged (not as root)
  * Drop all system-call capabilities
  * security-opt=no-new-privileges flag should be enabled when possible, user privileges are never escalated
* Number of requests per second is configurable
* Multi-threading
* Thread limiting; queue requests in-memory
* Commands:
  * Start
  * Pause
  * Stop
* Encrypted gRPC endpoint with compression in the security insight application
* Programming languages allowed:
  * Go
  * Rust
  * Python (T.B.D.)
* Scanner must be lightweight:
  * Storage: 50 MB max
  * Memory use: 250MB for 100 threads
  * CPU usage <20% CPU usage for 100 simultaneous threads

### Output

* Security insight title (summary)
* One or more function(s) and category/categories as described in the [NIST framework](https://nvlpubs.nist.gov/nistpubs/CSWP/NIST.CSWP.04162018.pdf) (page 30)
* Management summary with description and possible solution
* Technical details:
  * Advice how to solve
  * Assets involved
  * Detection date
  * References

### Quality and information security

* Must pass GitHub project security scanner checks
* Must pass code linting checks:
  * [GO](#)
  * [Rust](#)
  * [Python](#)
* Unit tests; 100% code coverage [Guardian360 DAO test standards](#)
