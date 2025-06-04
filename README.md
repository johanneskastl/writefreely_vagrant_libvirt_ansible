# writefreely_vagrant_libvirt_ansible

This Vagrant setup creates a VM and installs
[WriteFreely](https://writefreely.org) on it.

* The `main` branch uses the package that I created for openSUSE.
* The `upstream_binary` branch instead uses the binary and resources downloaded
  from the GitHub release.
* The `nginx` branch puts the whole setup behind a reverse proxy.

Default OS is openSUSE Leap 15.6, but that can be changed in the Vagrantfile.
Please be aware, that this might break the Ansible provisioning.

## Vagrant

1. You need vagrant obviously. And ansible. And git...
1. Fetch the Vagrant box, per default this is `opensuse/Tumbleweed.x86_64`,
   using `vagrant box add opensuse/Tumbleweed.x86_64`.
1. Make sure the git submodules are fully working by issuing `git submodule init
   && git submodule update`
1. Run `vagrant up`
1. Open the URL that Ansible printed out at the end of the provisioning. It
   should look something like `http://ghost.192.0.2.13.sslip.io`.
1. Click on the menu in the top left and log in using the credentials that were
   also printed out by Ansible (user name `vagrant-libvirt` with password
   `atotallysecurepassword`).
1. Write your first blog post and click on the "Send" icon on the top left.
1. Party!

## Cleaning up

The VM can be torn down after playing around using `vagrant destroy`.

## License

BSD-3-Clause

## Author Information

I am Johannes Kastl, reachable via git@johannes-kastl.de
