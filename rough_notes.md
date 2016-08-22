
# RHEL 6

​

- /usr/bin/oscap xccdf eval --profile server --results xccdf-results3.xml /usr/share/xml/scap/ssg/content/ssg-rhel6-xccdf.xml

​

- /usr/bin/oscap xccdf generate report xccdf-results3.xml > report3.html

​

# RHEL 7

​

- oscap xccdf eval --profile xccdf_org.ssgproject.content_profile_rht-ccp --results scan-xccdf-results2.xml /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml

​

- oscap xccdf generate report scan-xccdf-results2.xml  > ssg-report2.html

​

## tailoring als tweede stap

- oscap xccdf eval --profile xccdf_org.customer_profile_rht-ccp_tailored --results /root/openscap-rhel7/scan-xccdf-results7.xml --tailoring-file /usr/share/xml/scap/ssg/content/ssg-rhel7-ds-tailoring.xml  /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml

​

## tailoring all in one

​

- oscap xccdf eval --profile xccdf_org.customer_profile_rht-ccp_tailored --results /root/openscap-rhel7/scan-xccdf-results7.xml --report /var/www/html/index.html --tailoring-file /usr/share/xml/scap/ssg/content/ssg-rhel7-ds-tailoring.xml  /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml

​

​

#  profiles

​

[root@tst-vsu-tst-002 content]#  oscap info "/usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml"

Document type: Source Data Stream

Imported: 2015-10-02T12:17:44

​

Stream: scap_org.open-scap_datastream_from_xccdf_ssg-rhel7-xccdf-1.2.xml

RHEL 6

    /usr/bin/oscap xccdf eval –profile server –results xccdf-results3.xml /usr/share/xml/scap/ssg/content/ssg-rhel6-xccdf.xml

    /usr/bin/oscap xccdf generate report xccdf-results3.xml > report3.html

RHEL 7

    oscap xccdf eval –profile xccdf_org.ssgproject.content_profile_rht-ccp –results scan-xccdf-results2.xml /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml

    oscap xccdf generate report scan-xccdf-results2.xml > ssg-report2.html

tailoring als tweede stap

    oscap xccdf eval –profile xccdf_org.customer_profile_rht-ccp_tailored –results /root/openscap-rhel7/scan-xccdf-results7.xml –tailoring-file /usr/share/xml/scap/ssg/content/ssg-rhel7-ds-tailoring.xml /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml

tailoring all in one

    oscap xccdf eval –profile xccdf_org.customer_profile_rht-ccp_tailored –results /root/openscap-rhel7/scan-xccdf-results7.xml –report /var/www/html/index.html –tailoring-file /usr/share/xml/scap/ssg/content/ssg-rhel7-ds-tailoring.xml /usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml

profiles

[root@tst-vsu-tst-002 content]# oscap info “/usr/share/xml/scap/ssg/content/ssg-rhel7-ds.xml”
Document type: Source Data Stream
Imported: 2015-10-02T12:17:44

Stream: scap_org.open-scap_datastream_from_xccdf_ssg-rhel7-xccdf-1.2.xml
Generated: (null)
Version: 1.2
Checklists:
Ref-Id: scap_org.open-scap_cref_ssg-rhel7-xccdf-1.2.xml
Profiles:
xccdf_org.ssgproject.content_profile_standard
xccdf_org.ssgproject.content_profile_pci-dss
xccdf_org.ssgproject.content_profile_rht-ccp
xccdf_org.ssgproject.content_profile_common
xccdf_org.ssgproject.content_profile_stig-rhel7-server-upstream
Referenced check files:
ssg-rhel7-oval.xml
system: http://oval.mitre.org/XMLSchema/oval-definitions-5
Checks:
Ref-Id: scap_org.open-scap_cref_ssg-rhel7-oval.xml
Ref-Id: scap_org.open-scap_cref_output–ssg-rhel7-cpe-oval.xml
Ref-Id: scap_org.open-scap_cref_output–ssg-rhel7-oval.xml
Dictionaries:
Ref-Id: scap_org.open-scap_cref_output–ssg-rhel7-cpe-dictionary.xml
Bekijken van score (nagios checks)

benodigd: perl-XML-XPath rpm

[root@rhelserver openscap-rhel6]# xpath xccdf-results.xml '/Benchmark/TestResult/score/text()'
Found 1 nodes:
– NODE –
51.971725
[root@rhelserver openscap-rhel6]# xpath xccdf-results.xml '/Benchmark/TestResult/score'
Found 1 nodes:
– NODE –

<score system="urn:xccdf:scoring:default" maximum="100.000000">51.971725</score>

Het interpreteren van de score
