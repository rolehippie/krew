# workspace

[![Source Code](https://img.shields.io/badge/github-source%20code-blue?logo=github&logoColor=white)](https://github.com/rolehippie/krew)
[![General Workflow](https://github.com/rolehippie/krew/actions/workflows/general.yml/badge.svg)](https://github.com/rolehippie/krew/actions/workflows/general.yml)
[![Readme Workflow](https://github.com/rolehippie/krew/actions/workflows/docs.yml/badge.svg)](https://github.com/rolehippie/krew/actions/workflows/docs.yml)
[![Galaxy Workflow](https://github.com/rolehippie/krew/actions/workflows/galaxy.yml/badge.svg)](https://github.com/rolehippie/krew/actions/workflows/galaxy.yml)
[![License: Apache-2.0](https://img.shields.io/github/license/rolehippie/krew)](https://github.com/rolehippie/krew/blob/master/LICENSE)
[![Ansible Role](https://img.shields.io/badge/role-rolehippie.krew-blue)](https://galaxy.ansible.com/rolehippie/krew)

Ansible role to install krew plugin manager for kubectl.

## Sponsor

Building and improving this Ansible role have been sponsored by my current and previous employers like **[Cloudpunks GmbH](https://cloudpunks.de)** and **[Proact Deutschland GmbH](https://www.proact.eu)**.

## Table of content

- [Requirements](#requirements)
- [Default Variables](#default-variables)
  - [krew_extra_packages](#krew_extra_packages)
  - [krew_extra_plugins](#krew_extra_plugins)
  - [krew_general_packages](#krew_general_packages)
  - [krew_general_plugins](#krew_general_plugins)
  - [krew_install_path](#krew_install_path)
  - [krew_release_arch](#krew_release_arch)
  - [krew_release_download](#krew_release_download)
  - [krew_release_version](#krew_release_version)
- [Discovered Tags](#discovered-tags)
- [Dependencies](#dependencies)
- [License](#license)
- [Author](#author)

---

## Requirements

- Minimum Ansible version: `2.10`

## Default Variables

### krew_extra_packages

List of extra packages

#### Default value

```YAML
krew_extra_packages: []
```

#### Example usage

```YAML
krew_extra_packages:
  - foo
  - bar
  - baz
```

### krew_extra_plugins

List of extra plugins

#### Default value

```YAML
krew_extra_plugins: []
```

#### Example usage

```YAML
krew_extra_plugins:
  - plugin1
  - plugin2
  - name: plugin3
    state: absent
```

### krew_general_packages

List of general packages

#### Default value

```YAML
krew_general_packages:
  - git
```

#### Example usage

```YAML
krew_general_packages:
  - foo
  - bar
  - baz
```

### krew_general_plugins

List of general plugins

#### Default value

```YAML
krew_general_plugins:
  - images
  - ktop
  - neat
  - oidc-login
  - oomd
  - pexec
  - realname-diff
  - resource-versions
  - view-secret
  - whoami
```

#### Example usage

```YAML
krew_general_plugins:
  - plugin1
  - plugin2
  - name: plugin3
    state: absent
```

### krew_install_path

Path to install krew files into

#### Default value

```YAML
krew_install_path: /usr/share/krew
```

### krew_release_arch

Architecture for krew

#### Default value

```YAML
krew_release_arch: "{{ 'arm64' if ansible_architecture == 'aarch64' else 'amd64' }}"
```

### krew_release_download

URL to download krew from

#### Default value

```YAML
krew_release_download: 
  https://github.com/kubernetes-sigs/krew/releases/download/v{{ 
  krew_release_version }}/krew-linux_{{ krew_release_arch }}.tar.gz
```

### krew_release_version

Version of krew to install

#### Default value

```YAML
krew_release_version: 0.4.5
```

## Discovered Tags

**_krew_**

## Dependencies

- None

## License

Apache-2.0

## Author

[Thomas Boerger](https://github.com/tboerger)
