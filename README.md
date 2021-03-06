[![GitHub release][release-img]][release]
[![License][license-img]][license]
[![Coverage Status][cov-img]][cov]
[![Build Status][ci-img]][ci]

Docker-bench is a Go application that checks whether Docker is deployed securely by running the checks documented in the [CIS Docker Benchmark](https://www.cisecurity.org/benchmark/docker/).

Tests are configured with YAML files, making this tool easy to update as test specifications evolve. 


## CIS Docker Benchmark support

docker-bench currently supports tests as defined in the following CIS Docker Benchmarks:

| CIS Benchmark | docker-bench cfg directory | Docker versions |
|---|---|---|
| [Docker Benchmark v1.2.0](https://workbench.cisecurity.org/benchmarks/2351) | 18.09 | 18.09 and Docker Enterprise 2.1 |
| [Docker Community Edition Benchmark v1.1.0](https://workbench.cisecurity.org/benchmarks/552) | 17.06 | 17.06 |
| [Docker Benchmark v1.0.0](https://workbench.cisecurity.org/benchmarks/363) | 1.13.0 | 1.13.0 |

docker-bench will determine the test set to run based on the Docker version running on the host machine. 
The version to run tests for can also be specified manually with the `--version <ver>` commandline flag.

## Installation
### Installing from sources

Install [Go](https://golang.org/doc/install), then
clone this repository and run as follows (assuming your [$GOPATH is set](https://github.com/golang/go/wiki/GOPATH)):

```shell
go get github.com/aquasecurity/docker-bench
cd $GOPATH/src/github.com/aquasecurity/docker-bench
go build -o docker-bench .

# See all supported options
./docker-bench --help

# Run checks
./docker-bench

# Run checks for specified Docker version
./docker-bench --version 1.13.0

```

# Tests
Tests are specified in definition files `cfg/<version>/definitions.yaml`,
where `<version>` is the version of docker for which the test applies.

# Contributing
We welcome PRs and issue reports. 
Your PR is more likely to be accepted if it focuses on just one change.
Please include a comment with the results before and after your change.
Your PR is more likely to be accepted if it includes tests. (We have not historically been very strict about tests, but we would like to improve this!).
You're welcome to submit a draft PR if you would like early feedback on an idea or an approach.
Happy coding!

[cov-img]: https://codecov.io/github/aquasecurity/docker-bench/branch/master/graph/badge.svg
[cov]: https://codecov.io/github/aquasecurity/docker-bench
[ci-img]: https://travis-ci.com/aquasecurity/docker-bench.svg?branch=master
[ci]: https://travis-ci.com/aquasecurity/docker-bench
[license-img]: https://img.shields.io/badge/License-Apache%202.0-blue.svg
[license]: https://opensource.org/licenses/Apache-2.0
[release-img]: https://img.shields.io/github/release/aquasecurity/docker-bench.svg
[release]: https://github.com/aquasecurity/docker-bench/releases
