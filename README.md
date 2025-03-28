# Dell-iDRAC-7-Enterpise-Steps
iDrac 7 Enterprise Homelab Steps 

This works for all Dell IDRAC Servers that use IDRAC 7, This only works for IDRAC 7 and should not be used for businesses as this will make duplicate service tags and may cause issues if called for service from Dell.

This works great for Homelabs though!

This is tested on the 12th generation Poweredge servers, Dell PowerEdge R#20,T#20, for sure works on Dell R420(my current system) 


This is a remake from: https://pastebin.com/LQ8C7pgs

## Step 1
Download "OMSA71-CentOS6-x86_64-LiveDVD.iso". It must be this older version, newer versions replaced a tool we want with a dumbed down version. I have Provided a link to download it but you can also just google for it too as no files larger than 25mb can be uploaded to github.


### This first link Takes a long time
https://web.archive.org/web/20180106065924/http://linux.dell.com/files/openmanage-contributions/omsa-71-live/OMSA71-CentOS6-x86_64-LiveDVD.iso
### Offical Link for centos
https://vault.centos.org/6.10/isos/x86_64/


## Step 2

Using the ISO create a bootable drive and load into the operating system (This is a live ISO so you only need to boot to the live desktop and open the terminal)

## Step 3

Enter the following commands:

```bash
sudo su
```

```bash
smbios-sys-info --service-tag --set=9QYZF42
```

```bash
reboot now
```

When the system reboot it may come up with an license error or an upgrading screen but just let the system update and start IDRAC.

## Step 4

Login to IDRAC and it will want you to upload a license


Go ahead download the License.xml or use the following code and save it to a file.xml and upload it as a license.

You should now have IDRAC 7 Enterprise!

```xml
<?xml version="1.0"?>
<!--Copyright (c) 2010-2011 Dell Inc. All Rights Reserved.-->
<lns:LicenseClass xmlns:ds="http://www.w3.org/2000/09/xmldsig#" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:lns="http://www.dell.com/2011/12G/licensing">
  <lns:LicenseData>
    <lns:Schema lns:Vendor="Dell" lns:ID="iDRAC" lns:maxDepth="255" lns:SchemaVersion="2.0"/>
    <lns:TransferableLicense>true</lns:TransferableLicense>
    <lns:UTCdateSold>2013-07-30T03:04:11Z</lns:UTCdateSold>
    <lns:EntitlementID>DE00000009660549</lns:EntitlementID>
    <lns:DeviceClass lns:ID="iDRAC"/>
    <lns:ProductDescription>
      <lns:lang_en>iDRAC7 Enterprise License</lns:lang_en>
      <lns:lang_es>iDRAC7 Enterprise License</lns:lang_es>
      <lns:lang_fr>iDRAC7 Enterprise License</lns:lang_fr>
      <lns:lang_de>iDRAC7 Enterprise License</lns:lang_de>
      <lns:lang_it>iDRAC7 Enterprise License</lns:lang_it>
      <lns:lang_ja>iDRAC7 Enterprise License</lns:lang_ja>
      <lns:lang_zh>iDRAC7 Enterprise License</lns:lang_zh>
    </lns:ProductDescription>
    <lns:LicenseTerm>
      <lns:Perpetual/>
    </lns:LicenseTerm>
    <lns:Restrictions>
      <lns:ServiceTag>9QYZF42</lns:ServiceTag>
    </lns:Restrictions>
    <lns:DeviceInfo lns:ID="1" lns:VendorID="0x1912" lns:DeviceID="0x0011"/>
    <lns:Feature lns:ID="1" lns:Description="License Management" lns:Enabled="true"/>
    <lns:Feature lns:ID="2" lns:Description="RACADM" lns:Enabled="true"/>
    <lns:Feature lns:ID="3" lns:Description="WSMAN" lns:Enabled="true"/>
    <lns:Feature lns:ID="4" lns:Description="SNMP" lns:Enabled="true"/>
    <lns:Feature lns:ID="5" lns:Description="Auto Discovery" lns:Enabled="true"/>
    <lns:Feature lns:ID="6" lns:Description="USC Firmware Update" lns:Enabled="true"/>
    <lns:Feature lns:ID="7" lns:Description="Update Package" lns:Enabled="true"/>
    <lns:Feature lns:ID="8" lns:Description="USC Operating System Deployment" lns:Enabled="true"/>
    <lns:Feature lns:ID="9" lns:Description="USC Device Configuration" lns:Enabled="true"/>
    <lns:Feature lns:ID="10" lns:Description="USC Diagnostics" lns:Enabled="true"/>
    <lns:Feature lns:ID="11" lns:Description="Power Budget" lns:Enabled="true"/>
    <lns:Feature lns:ID="12" lns:Description="Power Monitoring" lns:Enabled="true"/>
    <lns:Feature lns:ID="13" lns:Description="Virtual Media" lns:Enabled="true"/>
    <lns:Feature lns:ID="14" lns:Description="Telnet" lns:Enabled="true"/>
    <lns:Feature lns:ID="15" lns:Description="SMASH CLP" lns:Enabled="true"/>
    <lns:Feature lns:ID="16" lns:Description="IPv6" lns:Enabled="true"/>
    <lns:Feature lns:ID="17" lns:Description="Dynamic DNS" lns:Enabled="true"/>
    <lns:Feature lns:ID="18" lns:Description="Dedicated NIC" lns:Enabled="true"/>
    <lns:Feature lns:ID="19" lns:Description="Directory Services" lns:Enabled="true"/>
    <lns:Feature lns:ID="20" lns:Description="Two-Factor Authentication" lns:Enabled="true"/>
    <lns:Feature lns:ID="21" lns:Description="Single Sign-On" lns:Enabled="true"/>
    <lns:Feature lns:ID="22" lns:Description="PK Authentication" lns:Enabled="true"/>
    <lns:Feature lns:ID="23" lns:Description="Crash Screen Capture" lns:Enabled="true"/>
    <lns:Feature lns:ID="24" lns:Description="Crash Video Capture" lns:Enabled="true"/>
    <lns:Feature lns:ID="25" lns:Description="Boot Capture" lns:Enabled="true"/>
    <lns:Feature lns:ID="26" lns:Description="Virtual Console" lns:Enabled="true"/>
    <lns:Feature lns:ID="27" lns:Description="Virtual Flash Partitions" lns:Enabled="true"/>
    <lns:Feature lns:ID="28" lns:Description="Console Collaboration" lns:Enabled="true"/>
    <lns:Feature lns:ID="29" lns:Description="Device Monitoring" lns:Enabled="true"/>
    <lns:Feature lns:ID="30" lns:Description="Remote Inventory" lns:Enabled="true"/>
    <lns:Feature lns:ID="31" lns:Description="Storage Monitoring" lns:Enabled="true"/>
    <lns:Feature lns:ID="32" lns:Description="Remote Firmware Update" lns:Enabled="true"/>
    <lns:Feature lns:ID="33" lns:Description="Remote Firmware Configuration" lns:Enabled="true"/>
    <lns:Feature lns:ID="34" lns:Description="Remote Inventory Export" lns:Enabled="true"/>
    <lns:Feature lns:ID="35" lns:Description="Remote Operating System Deployment" lns:Enabled="true"/>
    <lns:Feature lns:ID="36" lns:Description="Backup and Restore" lns:Enabled="true"/>
    <lns:Feature lns:ID="37" lns:Description="Part Replacement" lns:Enabled="true"/>
    <lns:Feature lns:ID="38" lns:Description="SSH" lns:Enabled="true"/>
    <lns:Feature lns:ID="39" lns:Description="Remote File Share" lns:Enabled="true"/>
    <lns:Feature lns:ID="40" lns:Description="Virtual Folders" lns:Enabled="true"/>
    <lns:Feature lns:ID="41" lns:Description="Web GUI" lns:Enabled="true"/>
    <lns:Feature lns:ID="42" lns:Description="Network Time Protocol" lns:Enabled="true"/>
    <lns:Feature lns:ID="43" lns:Description="Email Alerts" lns:Enabled="true"/>
    <lns:Feature lns:ID="44" lns:Description="Security Lockout" lns:Enabled="true"/>
    <lns:Feature lns:ID="45" lns:Description="Remote Syslog" lns:Enabled="true"/>
    <lns:Feature lns:ID="253" lns:Description="Integrated Dell Remote Access Controller 7 Enterprise" lns:Enabled="true"/>
  </lns:LicenseData>
<dsig:Signature xmlns:dsig="http://www.w3.org/2000/09/xmldsig#">
<dsig:SignedInfo>
<dsig:CanonicalizationMethod Algorithm="http://www.w3.org/2001/10/xml-exc-c14n#"/>
<dsig:SignatureMethod Algorithm="http://www.w3.org/2000/09/xmldsig#rsa-sha1"/>
<dsig:Reference URI="">
<dsig:Transforms>
<dsig:Transform Algorithm="http://www.w3.org/2000/09/xmldsig#enveloped-signature"/>
</dsig:Transforms>
<dsig:DigestMethod Algorithm="http://www.w3.org/2000/09/xmldsig#sha1"/>
<dsig:DigestValue>jEuefYR4MBMs4Ucd9WbRjihpZe4=</dsig:DigestValue>
</dsig:Reference>
</dsig:SignedInfo>
<dsig:SignatureValue>P7vr8XFES9T4w+c9Z6uQPq9muMpGv0Dj44El2coPPrkHkkNz5YdZ2qY9vXo+3gcb
HdLT0e1/s99zfgIwWPfg9fT/XbAr831+pPynhNDRaUoFr93PGA3KmMFOarL8Fe9e
DQZp4pIkaPsDfZtkqcUevdKpTRYf+98ZU9advk3Q+yDdyyTHuhTqTw91McglPJLc
R6ckZ2N1uMPKdSXp7pVDBLE0X8VVLliCG4NL8ro2B4p1wBzUYXWHRm8arIzwTyWI
c3RmnqcwrKoVHF3SabgUf0ALAtICYk3dR3lI5tYm8Bzkdk+b89JXZx/jkdHvRrx6
kY9hX72aH2dJxdk1DzEbCw==</dsig:SignatureValue>
<dsig:KeyInfo>
<dsig:X509Data>
<dsig:X509Certificate>MIIDTjCCAjagAwIBAgIBATANBgkqhkiG9w0BAQUFADBRMRMwEQYDVQQKEwpEZWxs
LCBJbmMuMSEwHwYDVQQLExhFbWJlZGRlZCBMaWNlbnNlIE1hbmFnZXIxFzAVBgNV
BAMTDkNBIENlcnRpZmljYXRlMB4XDTEwMDEwMTAwMDAwMFoXDTM1MTIzMTIzNTk1
OVowVjETMBEGA1UEChMKRGVsbCwgSW5jLjEhMB8GA1UECxMYRW1iZWRkZWQgTGlj
ZW5zZSBNYW5hZ2VyMRwwGgYDVQQDExNTaWduaW5nIENlcnRpZmljYXRlMIIBIjAN
BgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAqbRo2DZtkjxl5YtqD5ePYdzrWbkU
YQJwVaWYe1tE7ZAdou5TLTsjPnaa1cLcPTexn+cq8YjukIVwkwJP7yJ5GkrYGUnf
0Q6unWWgwcgTStlpflz31e8AbxXqNYZEFvEktojYS0kAfiYES+H02GUU5PtV7B9Y
BbtZEowU2DPuqRGG1FF8mAsp1vojcbQGx+nS2Of47oQJRrJlh28COXyf2w/+IRAz
RmeYin+9pisfrT9fmlUtxa7sAAV/KZFRx8ED31YiktXgI/u/PNnHlchiCMaL6pzA
HMBf115O7A2y6IZ9sXUHvH8V9QnDkWT1XHMn8GCW8HXOA5zA232OxiaRmQIDAQAB
oywwKjAJBgNVHRMEAjAAMB0GA1UdDgQWBBQAoZ7yMjDHMAFtmmmO/zyz3BJ6hjAN
BgkqhkiG9w0BAQUFAAOCAQEAHHgoOg57S+lAEejahdBE1HMwe6BF3b9bzUMCynn9
7buXa3cnRFO3H3674WKU6nBjv4nkT3qMyXwgi7MvXcu69msK4eM6QA8XeC7G1rD+
2bb/ENR9R9Zo0BWLym/ij8uUA/BzX8hnbzWxN82+FMdY9WD4fJAJwJ5ZPEbU1Vfy
7wOWosHgDPXjeAhlhkxDQi6vlRTJdfED6tBY7iGD4AQXfzrHzAZpZlIvKbM2c54B
65wMSlqfEWMBDhT5qcwGCq82hmi7/sCtu9Z20g2s9F0fp4XlGX8L7l0hCa46zjay
37GffYsScEDFg/DmkIpcXnGzyx8l1msLzpj8Gt4zHhPlgA==</dsig:X509Certificate>
</dsig:X509Data>
</dsig:KeyInfo>
</dsig:Signature></lns:LicenseClass>
```
