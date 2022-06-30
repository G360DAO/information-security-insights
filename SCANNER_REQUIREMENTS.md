# Scanner Requirements

In addition to the [Generic requirements](GENERIC_REQUIREMENTS.md), scanners should also meet the following requirements.

* Amount of requests per second PER IP-address must be configurable
* Maximum amount of concurrent requests per scan job must be configurable
* Must be able to scan multiple hosts concurrently (i.e. 100 threads)
* Output should contain:
  * Technical risk level
  * Hostname
  * IP address
  * Port
  * Protocol
  * CVE's covered (where applicable)
  * CVSSv3 score (where applicable)
  * Scanner name (max 80 character scanner "name" description)
  * Full description of issue detected by scanner
  * Full solution for detected issue by scanner
