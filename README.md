Stouts.ruby
=============

[![Build Status](http://img.shields.io/travis/Stouts/Stouts.ruby.svg?style=flat-square)](https://travis-ci.org/Stouts/Stouts.ruby)
[![Galaxy](http://img.shields.io/badge/galaxy-Stouts.ruby-blue.svg?style=flat-square)](https://galaxy.ruby.com/list#/roles/1629)
[![Tag](http://img.shields.io/github/tag/Stouts/Stouts.ruby.svg?style=flat-square)]()

Ansible role which manage ruby (install, setup, gems)

#### Variables

```yaml
ruby_enabled: yes                   # The role is enabled
ruby_version: 1.9.3                 # Set ruby version (1.9.3, 2.0.0, 2.1.2)
ruby_gems: []                       # List of gems which will be installed
ruby_apt_dependencies:
- autoconf
- build-essential
- libreadline-dev
- libssl-dev
- libyaml-dev
- zlib1g-dev

ruby_versions:
  1.9.3:
    version: 1.9.3-p545
    download_location: http://cache.ruby-lang.org/pub/ruby/1.9/ruby-1.9.3-p545.tar.gz
  2.0.0:
    version: 2.0.0-p481
    download_location: http://cache.ruby-lang.org/pub/ruby/2.0/ruby-2.0.0-p481.tar.gz
  2.1.2:
    version: 2.1.2
    download_location: http://cache.ruby-lang.org/pub/ruby/2.0/ruby-2.1.2.tar.gz

ruby_current: "{{ ruby_versions[ruby_version] }}"
```

#### Usage

Add `Stouts.ruby` to your roles and set vars in your playbook file.

Example:

```yaml

- hosts: all

  roles:
    - Stouts.ruby

  vars:
    ruby_version: 2.0.0
```

#### License

Licensed under the MIT License. See the LICENSE file for details.

#### Feedback, bug-reports, requests, ...

Are [welcome](https://github.com/Stouts/Stouts.ruby/issues)!
