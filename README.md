[![build-test](https://github.com/darkwizard242/ansible-role-hadolint/workflows/build-and-test/badge.svg?branch=master)](https://github.com/darkwizard242/ansible-role-hadolint/actions?query=workflow%3Abuild-and-test) [![release](https://github.com/darkwizard242/ansible-role-hadolint/workflows/release/badge.svg)](https://github.com/darkwizard242/ansible-role-hadolint/actions?query=workflow%3Arelease) ![Ansible Role](https://img.shields.io/ansible/role/57396?color=dark%20green%20) ![Ansible Role](https://img.shields.io/ansible/role/d/57396?label=role%20downloads) ![Ansible Quality Score](https://img.shields.io/ansible/quality/57396?label=ansible%20quality%20score) [![Quality Gate Status](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-hadolint&metric=alert_status)](https://sonarcloud.io/dashboard?id=ansible-role-hadolint) [![Maintainability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-hadolint&metric=sqale_rating)](https://sonarcloud.io/dashboard?id=ansible-role-hadolint) [![Reliability Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-hadolint&metric=reliability_rating)](https://sonarcloud.io/dashboard?id=ansible-role-hadolint) [![Security Rating](https://sonarcloud.io/api/project_badges/measure?project=ansible-role-hadolint&metric=security_rating)](https://sonarcloud.io/dashboard?id=ansible-role-hadolint) ![GitHub tag (latest SemVer)](https://img.shields.io/github/tag/darkwizard242/ansible-role-hadolint?label=release) ![GitHub repo size](https://img.shields.io/github/repo-size/darkwizard242/ansible-role-hadolint?color=orange&style=flat-square)

# Ansible Role: hadolint

Role to install (_by default_) `hadolint` on **Debian/Ubuntu** and **EL** systems. [hadolint](https://github.com/hadolint/hadolint) is a smart Dockerfile linter that helps you build best practice Docker images.

## Requirements

None.

## Role Variables

Available variables are listed below (located in `defaults/main.yml`):

### Variables list:

```yaml
hadolint_app: hadolint
hadolint_version: 2.12.0
hadolint_os: Linux
hadolint_arch: x86_64
hadolint_dl_url: https://github.com/{{ hadolint_app }}/{{ hadolint_app }}/releases/download/v{{ hadolint_version }}/{{ hadolint_app }}-{{ hadolint_os }}-{{ hadolint_arch }}
hadolint_bin_path: "/usr/local/bin"
hadolint_bin_permission_mode: '0755'
```

### Variables table:

Variable                     | Description
---------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------
hadolint_app                 | Defines the app to install i.e. **hadolint**
hadolint_version             | Defined to dynamically fetch the desired version to install. Defaults to: **2.12.0**
hadolint_os                  | Defines os type. Defaults to: **Linux**
hadolint_arch                | Defines os architecture. Defaults to: **x86_64**
hadolint_dl_url              | Defines URL to download the hadolint binary from.
hadolint_bin_path            | Defined to dynamically set the appropriate path to store hadolint binary into. Defaults to (as generally available on any user's PATH): **/usr/local/bin**
hadolint_bin_permission_mode | Defines the permission mode level for the file. Defaults to: `0755`

## Dependencies

None

## Example Playbook

For default behaviour of role (i.e. installation of **hadolint**) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.hadolint
```

For customizing behavior of role (i.e. specifying the desired **hadolint** version) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.hadolint
  vars:
    hadolint_version: 2.7.0
```

For customizing behavior of role (i.e. placing binary of **hadolint** package in different location) in ansible playbooks.

```yaml
- hosts: servers
  roles:
    - darkwizard242.hadolint
  vars:
    hadolint_bin_path: /bin/
```

## License

[MIT](https://github.com/darkwizard242/ansible-role-hadolint/blob/master/LICENSE)

## Author Information

This role was created by [Ali Muhammad](https://www.alimuhammad.dev/).
