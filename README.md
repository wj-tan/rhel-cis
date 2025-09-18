# rhel-cis

## CIS hardening with OSCAP 

1. Head to https://access.redhat.com/downloads/content/479/ver=/rhel---8/8.3/x86_64/packages to download the `scap-security-guide` for your rhel version
2. `dnf install -y openscap-scanner scap-security-guide`
3. `dnf localinstall <scap-security-guide>.rpm`

Reference : https://www.redhat.com/en/blog/center-internet-security-cis-compliance-red-hat-enterprise-linux-using-openscap
