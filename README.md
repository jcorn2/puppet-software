software
=============

[![Puppet Forge](http://img.shields.io/puppetforge/v/edestecd/software.svg)](https://forge.puppetlabs.com/edestecd/software)
[![Issue stats](http://issuestats.com/github/edestecd/puppet-software/badge/pr?style=flat)](http://issuestats.com/github/edestecd/puppet-software)

####Table of Contents

1. [Overview](#overview)
2. [Module Description - What the module does and why it is useful](#module-description)
3. [Setup - The basics of getting started with software](#setup)
    * [What software affects](#what-software-affects)
    * [Setup requirements](#setup-requirements)
    * [Beginning with software](#beginning-with-software)
4. [Usage - Configuration options and additional functionality](#usage)
5. [Reference - An under-the-hood peek at what the module is doing and how](#reference)
5. [Limitations - OS compatibility, etc.](#limitations)
6. [Development - Guide for contributing to the module](#development)

##Overview

Puppet Module to install various Desktop Software

##Module Description

The software module provides various classes to install many commonly needed Desktop Applications.  
Many of these applications require little or no configuration and are mostly Graphical.
This module provides a quick way to get many repetitive apps installed.

Other modules exist for many of these applications and I have used some of them  
as examples, but I prefer to manage these in one module.
Each application has a class, which you may include separately to install  
exactly the applications you desire.

##Setup

###What software affects

only installs apps (OS X) and packages (Ubuntu)

###Setup Requirements

only need to install the module

###Beginning with software

Install only Google Chrome browser:

```puppet
include software::browsers::chrome
```

##Usage

###Install various apps

```puppet
include software::browsers::chrome
include software::browsers::firefox
include software::database::pgcommander
include software::database::sequelpro
include software::editors::sourcetree
include software::editors::textmate
include software::entertainment::vlc
include software::idesdk::android_sdk
include software::prefpanes::hosts
include software::prefpanes::launchrocket
include software::social::skype
include software::storage::drive
include software::storage::fetch
include software::utilities::alfred
include software::utilities::controlplane
include software::utilities::iterm
include software::utilities::onyx
include software::virtualization::virtualbox
include software::webstack::anvil
```

###Install everything in the browser group

```puppet
include software::browsers
```

###Install apps with hiera yaml

```puppet
hiera_include('classes')
```
```yaml
---
classes:
- software::browsers::chrome
- software::entertainment::vlc
- software::social::skype
```

##Reference

### Classes

* browsers
* database
* editors
* entertainment
* social

##Limitations

Some proprietary software requires licenses.  
You may need to pass these license keys and possibly urls to use those classes.

This module has been built on and tested against Puppet 3.2.4 and higher.  
While I am sure other versions work, I have not tested them.

This module supports modern OS X and Ubuntu systems.  
This module has been tested on OS X 10.9 "Mavericks" and Ubuntu 14.04.

No plans to support other versions (unless you add it :)..

##Development

Pull Requests welcome

##Contributors

Chris Edester (edestecd)