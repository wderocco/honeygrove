![Honeygrove](https://github.com/UHH-ISS/honeygrove/raw/master/wiki_resources/honeygrove_logo.png)

Honeygrove is a modular honeypot based on Python that builds upon [Broker](https://github.com/zeek/broker) and the [Twisted Framework](https://twistedmatrix.com/trac/wiki).

## System Requirements

Honeygrove currently requires **Python 3.5+** and was tested on Ubuntu 16.4, Debian 9.1 and ArchLinux. However it should work on other distributions that provide a compatible Python distribution. If Broker is not available, the honeypot itself can be used without it. Currently there is no possibility to communicate with the management-console or the monitoring stack without Broker.


## Quickstart Guide

* Clone the repository or download and unzip it
* Optional: Setup a virtualenv to contain the required dependencies
  ```shell
  $ python3 -m venv .venv
  $ source .venv/bin/activate
  ```
* Install the required python dependencies
  ```shell
  $ pip3 install --upgrade -r requirements.txt
  ```
* Optional: Install [`broker`](https://github.com/zeek/broker) and the python bindings to communicate with a CIM
* Create the honeygrove main directory and some required subdirectories
  ```shell
  $ mkdir -p /var/honeygrove/{logs,resources/{quarantine,honeytoken_files}}
  ```
* Copy the provided example resources to the main directory
  ```shell
  $ cp -a resources /var/honeygrove
  ```
* Edit the configuration file to fit your needs
  ```shell
  $ $EDITOR honeygrove/config.py
  ```
* Start honeygrove and verify everything works as expected
  ```shell
  $ sudo python3 -m honeygrove
  ```

For further information see our [wiki](https://github.com/UHH-ISS/honeygrove/wiki) (currently only the user guide for honeygrove is available in english).


## Related Projects

Honeygrove is intended to be used with a Cyber Incident Monitor (CIM) ([honeygrove-cim](https://github.com/UHH-ISS/honeygrove-cim)) and can additionally be controlled through a management console ([honeygrove-console](https://github.com/UHH-ISS/honeygrove-console)) that communicates with honeygrove via `broker`.

## License

Honeygrove is licensed under the MIT license. See LICENSE for more details.

