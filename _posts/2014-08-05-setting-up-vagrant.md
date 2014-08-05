---
layout: post
title:  "Setting Up Vagrant"
date:   2014-08-05 09:43:00
categories:
- blog
- vagrant
---

A few months ago, I started using [Vagrant](http://www.vagrantup.com/). It's an excellent tool that allows you to create custom VM environments, and pairs together well with the free [Virtual Box](https://www.virtualbox.org/).

I created my own custom Ubuntu Server 14.04 box, with the intent to serve as a web development environment with the following packages installed:

- MySQL
- node.js
- Ruby
- Sass
- Compass
- Jekyll
- Git

Vagrant allowed me to set this all up just once, and I can tear it down and rebuild the VM, with all the packages I need with just a single command.

To get this working, first install Vagrant and Virtual Box. Create a folder for the box and do:

``` bash
$ vagrant init marty/trusty64
```

<!--more-->

Alternatively, you can replace `marty/trusty64` with another [box](https://vagrantcloud.com/discover/featured) if you prefer a different OS or a vanilla version of Ubuntu.

This will create a `Vagrantfile` which can be edited to further customize the setup, like portforwarding or sharing folders between the host and client VM. Check Vagrant's [documentation](http://docs.vagrantup.com/v2/) for more information.

Then:

``` bash
$ vagrant up
```

Vagrant will then begin to download the VM image, and once finished, will perform the necessary installation and setup based on your `Vagrantfile`.

To gain access to the VM shell:

``` bash
$ vagrant ssh
```

Once you're finished, exit the shell. And to shut down the VM:

``` bash
$ vagrant halt
```

To delete the VM:

``` bash
$ vagrant destroy
```

If you need another box, repeat the steps above and the environment will be replicated.

So awesome.