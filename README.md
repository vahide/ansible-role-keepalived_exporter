# Ansible Role: keepalived_exporter

[![Build Status](https://travis-ci.com/cloudalchemy/ansible-keepalived_exporter.svg?branch=master)](https://travis-ci.com/cloudalchemy/ansible-keepalived_exporter)
[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)
[![Ansible Role](https://img.shields.io/badge/ansible%20role-cloudalchemy.keepalived_exporter-blue.svg)](https://galaxy.ansible.com/cloudalchemy/keepalived_exporter/)
[![GitHub tag](https://img.shields.io/github/tag/cloudalchemy/ansible-keepalived_exporter.svg)](https://github.com/cloudalchemy/ansible-keepalived_exporter/tags)

## Description

Deploy [keepalived_exporter](https://github.com/prometheus/keepalived_exporter) using ansible.

## Requirements

- Ansible >= 2.7 (It might work on previous versions, but we cannot guarantee it)

## Role Variables

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file as well as in table below.

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `keepalived_exporter_web_listen_address` | "0.0.0.0:9165" | Address on which keepalived_exporter will listen |

## Example

### Playbook

Use it in a playbook as follows:
```yaml
- hosts: all
  roles:
    - ansible-role-keepalived_exporter
```

## Local Testing

The preferred way of locally testing the role is to use Docker and [molecule](https://github.com/metacloud/molecule) (v2.x). You will have to install Docker on your system. See "Get started" for a Docker package suitable to for your system.
We are using tox to simplify process of testing on multiple ansible versions. To install tox execute:
```sh
pip3 install tox
```
To run tests on all ansible versions (WARNING: this can take some time)
```sh
tox
```
To run a custom molecule command on custom environment with only default test scenario:
```sh
tox -e py35-ansible28 -- molecule test -s default
```
For more information about molecule go to their [docs](http://molecule.readthedocs.io/en/latest/).

If you would like to run tests on remote docker host just specify `DOCKER_HOST` variable before running tox tests.

## Travis CI

Combining molecule and travis CI allows us to test how new PRs will behave when used with multiple ansible versions and multiple operating systems. This also allows use to create test scenarios for different role configurations. As a result we have a quite large test matrix which will take more time than local testing, so please be patient.

## Contributing

See [contributor guideline](CONTRIBUTING.md).

## Troubleshooting

See [troubleshooting](TROUBLESHOOTING.md).

## License

This project is licensed under MIT License. See [LICENSE](/https://github.com/vahide/ansible-role-keepalived_exporter/LICENSE)
