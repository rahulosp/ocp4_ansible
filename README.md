## OpenShift 4 Ansible tasks and Jinja templates for Bastion/Helper Node setup

Here is the directory structure of all the files in this directory:

```bash
$ tree
.
├── LICENSE
├── README.md
├── ansible.cfg
├── files
│   └── set-dns-serial.sh
├── handlers
│   └── main.yml
├── inventory
├── tasks
│   ├── configure_bind_dns.yml
│   ├── configure_dhcpd.yml
│   ├── configure_haproxy_lb.yml
│   └── configure_tftp_pxe.yml
├── templates
│   ├── default.j2
│   ├── dhcpd-uefi.conf.j2
│   ├── dhcpd.conf.j2
│   ├── haproxy.cfg.j2
│   ├── named.conf.j2
│   ├── pxe-bootstrap.j2
│   ├── pxe-master.j2
│   ├── pxe-worker.j2
│   ├── reverse.j2
│   └── zonefile.j2
└── vars
    └── main.yml

5 directories, 21 files
```

The `tasks` folder contain all the tasks to configure:
- Bind DNS server
- DHCP Server
- HAProxy Load balancer
- PXE / TFTP Server

### Setting variables
Modify `vars/main.yml` and set all required variables for configuring DNS, DHCP, HAProxy and TFTP/PXE boot.

```bash
vim vars/main.yml
```

### Running the tasks with Ansible

This tasks in this repository are to create an environment for OCP install. Official RHEL guide needs to be followed for further instructions.
