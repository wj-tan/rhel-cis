# Experiment done on RHEL 9.6

## Partition during RHEL installation

/boot/efi       600M   vfat    (EFI System Partition)

/boot           1G     xfs

/               20G    xfs

swap            4G     swap

/home           10G    xfs

/var            10G    xfs

/var/log        8G     xfs

/var/log/audit  4G     xfs

/tmp            4G     xfs

/var/tmp        4G     xfs

## Ansible requirments for running the playbook remediation
Ansible Core 2.14.18

Community General 9.5.11

Posix 1.5.4
