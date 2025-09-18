# Experiment done on RHEL 9.6

## Partition during RHEL installation

/boot/efi       600M   vfat    (EFI System Partition)

/boot           2G     xfs

/               20G    xfs

swap            2G     swap

/home           5G    xfs

/var            5G    xfs

/var/log        10G     xfs

/var/log/audit  5G     xfs

/tmp            4G     xfs

/var/tmp        4G     xfs

## Ansible requirments for running the playbook remediation
Ansible Core 2.16.3

Community General 11.3.0

Posix 2.1.0
