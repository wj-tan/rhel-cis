# rhel-cis

## CIS hardening with OSCAP 

### L1 Server
1. Head to https://access.redhat.com/downloads/content/479/ver=/rhel---8/8.3/x86_64/packages to download the `scap-security-guide` for your rhel version
   
2. ```bash
   dnf install -y openscap-scanner scap-security-guide
   ```
   
3. ```bash
   dnf localinstall <scap-security-guide>.rpm
   ```
   
4. Run a CIS Level 1 Server scan with OSCAP
   ```bash
   sudo oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_cis_server_l1 --results /root/cis-l1-scan-results-before.xml --report /root/cis-l1-report-before.html /usr/share/xml/scap/ssg/content/ssg-rhel9-ds.xml
   ```
   
5. Generate remediation ansible playbook
   ```bash
   sudo oscap xccdf generate fix --fix-type ansible --output PlaybookToRemediate.yml --result-id "" cis-l1-scan-results-before.xml`
   ```
    
6. Generate remediation bash script
   ```bash
   sudo oscap xccdf generate fix --fix-type bash --output BashToRemediate.sh --result-id "" cis-l1-scan-results-before.xml
   ```

7. Run remediation bash script or ansible playbook
   
8. Run a scan again to generate new report
   ```bash
   sudo oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_cis_server_l1 --results /root/cis-l1-scan-results-after.xml --report /root/cis-l1-report-after.html /usr/share/xml/scap/ssg/content/ssg-rhel9-ds.xml
   ```

Reference : https://www.redhat.com/en/blog/center-internet-security-cis-compliance-red-hat-enterprise-linux-using-openscap

### Tested On

1. Rhel 9.6
