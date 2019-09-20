# 2019lugano
Training in Lugano


https://www.ibm.com/support/knowledgecenter/STXKQY/uid_gpfs.pdf

http://schulung.t3isp.de/documents/linux-security.pdf

```
### OSSEC - lokal ###
yum install epel-release 
yum install -y gcc inotify-tools zlib-devel wget unzip 
cd /usr/src 
 wget https://github.com/ossec/ossec-hids/archive/3.3.0.zip
 unzip 3.3.0.zip 
 cd ossec-hids-3.3.0/
 wget https://ftp.pcre.org/pub/pcre/pcre2-10.32.tar.gz
 tar xzf pcre2-10.32.tar.gz -C src/external
 ./install.sh 
 ```

Changing the ossec.conf file 
(right after syscheck) 

```
<syscheck>
 <frequency>60</frequency>
    <alert_new_files>yes</alert_new_files>

 <!-- Directories to check  (perform all possible verifications) -->
    <directories check_all="yes" report_changes="yes" realtime="yes">/etc,/usr/bin,/usr/sbin</directories>
    <directories check_all="yes" report_changes="yes" realtime="yes">/bin,/sbin,/boot</directories>
```

```
# change in rules/local_rules.xml 
  <rule id="554" level="7" overwrite="yes">
    <category>ossec</category>
    <decoded_as>syscheck_new_entry</decoded_as>
    <description>xFile added to the system.</description>
    <group>syscheck,</group>
  </rule>
```

### Journald ###

```
Creating it persistantly
mkdir /var/log/journal 
systemctl restart systemd-journald

### selinux ### 

https://www.amazon.de/gp/product/B01LWM02WI/ref=ppx_yo_dt_b_search_asin_title?ie=UTF8&psc=1

### disable usb-storage ###

https://www.rootusers.com/how-to-disable-usb-storage-devices-in-linux/

### working with udev ###

https://github.com/jmetzger/2019lugano/blob/master/README.md

Locking out port scanners:
https://unix.stackexchange.com/questions/345114/how-to-protect-against-port-scanners

wget --no-check-certificate http://www.exploit-db.com/download/8572
