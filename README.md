# 2019lugano
Training in Lugano


https://www.ibm.com/support/knowledgecenter/STXKQY/uid_gpfs.pdf

http://schulung.t3isp.de/documents/linux-security.pdf

```
### OSSEC - lokal ###
yum install epel-release 
yum install -y gcc inotify-tools zlib-devel wget
cd /usr/src 
 wget https://github.com/ossec/ossec-hids/archive/3.3.0.zip
 unzip 3.3.0.zip 
 cd ossec-hids-3.3.0/
 wget https://ftp.pcre.org/pub/pcre/pcre2-10.32.tar.gz
 tar xzf pcre2-10.32.tar.gz -C src/external
 ./install.sh 
 ```
