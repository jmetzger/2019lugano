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
