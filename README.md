Home Server
===========

Notes on setting up a simple basement server for media serving and camera monitoring.

Hardware is an [HP Compaq 6000 Pro][1], purchased on Kijiji and upgraded with a pair of 2 TB
hard drives. The OS is running from the stock drive, and is Ubuntu 16.04, installed via the [netboot iso][2].

[1]: https://www.cnet.com/products/hp-compaq-6000-pro-core-2-quad-q9400-2-66-ghz-monitor-none-series/specs/
[2]: http://archive.ubuntu.com/ubuntu/dists/xenial/main/installer-amd64/current/images/netboot/mini.iso

Ensure that your user has sudo permissions, and push your SSH key to the machine:

```
cat ~/.ssh/id_rsa.pub | ssh mike@kokiri "mkdir ~/.ssh; cat >> ~/.ssh/authorized_keys"
```

Ansible
-------

```
ansible-playbook playbook.yaml --ask-sudo-pass
```


