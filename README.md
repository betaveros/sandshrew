# sandshrew

sandshrew is a prototype concolic unit testing tool for cryptographic verification. It harnesses the [Manticore](https://github.com/trailofbits/manticore) API in order to perform unconstrained concolic execution on C cryptographic primitives.

Classical symbolic execution is generally not feasible when analyzing crypto, due to the presence of complex symbolic expressions. sandshrew fixes this problem and ensures functional correctness by concretizing (or, "emulating") the execution of specified cryptographic primitives, avoiding complex SMT queries and creating a speedup in the analysis.

## Features

* Automatic testcase generation for analysis
* Easy interface for writing unit test cases
* Integration into development workflows (imagine formal verification for unit testing)
* 300 LOCs

## Installation

```
$ git clone https://github.com/trailofbits/sandshrew && cd sandshrew/
$ python setup.py install
```

To hack and develop on sandshrew, it is recommended to utilize a Python `virtualenv`.

## Quickstart

The simplest example is the hash collision example in `test_openssl_md5.c`:

```
$ cd examples/
$ make all && cd ..
$ sandshrew -t examples/test_openssl_md5 --debug
```

## More Help

Drop by the [wiki](https://github.com/trailofbits/sandshrew/wiki) for more information about getting started and writing test cases.

sandshrew is __currently experimental__, and has not been extensively tested for larger test cases.

## License

sandshrew is licensed and distributed under the MIT license
