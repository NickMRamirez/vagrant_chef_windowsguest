About
=====
This project shows creating a guest VM with Vagrant and then provisioning it with Chef. 
The VM already has the Chef client installed on it.

Issues
=====
Currently, I must override some paths or else Vagrant tries to use Linux-style paths (e.g. /tmp/vagrant-chef).
See [https://github.com/mitchellh/vagrant/issues/5862](https://github.com/mitchellh/vagrant/issues/5862)