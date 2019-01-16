## �Х�ӽҰ�W�m�ߡA�z�Lsystemd�޲z�G��sshd�A�ȡA�����ĤG��sshd�A�Ȫ� port ���� 2222�C������i�H�ϥΫ��O netstat -alntp | grep ssh �T�{�O�_�ҰʤG��sshd�A�ȡA�d�Ҧp�U�G
```
$ netstat -alntp | grep ssh
tcp        0      0 0.0.0.0:22     0.0.0.0:*     LISTEN      1300/sshd
tcp        0      0 0.0.0.0:2222   0.0.0.0:*     LISTEN      15275/sshd
tcp6       0      0 :::22          :::*          LISTEN      1300/sshd
tcp6       0      0 :::2222        :::*          LISTEN      15275/sshd
```
```
Note 1: CentOS���ϥ�SELinux �A�G�w�]�u���\ SSH �ϥΰ� 22�A�Y�n�ϥΰ� 2222�A�ϽХΤU�C���}�Ҩ��ˬd


$ semanage port -a -t ssh_port_t -p tcp 2222
$ semanage port -l | grep ssh
ssh_port_t tcp 2202, 22


Note 2: CentOS�w�]��������firewalld�|�T��X�ݰ�2222�A�Y�n�z�L2222��sssh�A�Х�����firewalld�C
```

### Ans:
```
cd /etc/ssh
cp sshd_config sshd2_config (�Nsshd_config�����e�ƻs��sshd2_config)
```
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/1.PNG?raw=true)


```
vi sshd2_config (�s��sshd2_config)
�N (Port 22) �אּ (Port 2222)
```
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/2.PNG?raw=true)
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/3.PNG?raw=true)

```
cd /etc/systemd/system
cp /usr/lib/systemd/system/sshd.service sshd2.service (�Nsshd.service�����e�ƻs��sshd2.service)
```
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/4.PNG?raw=true)

```
vi sshd2.service (�s��sshd2.service)
�N "Type" �令 simple (�쬰notify)
�N "ExecStart" �����e�令 /usr/sbin/sshd -f /etc/ssh/sshd2_config -D $OPTIONS
```
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/5.PNG?raw=true)
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/6.PNG?raw=true)

```
yum install policycoreutils-python (������N��ϥ� semanage �F)
```
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/7.PNG?raw=true)
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/8.PNG?raw=true)

```
semanage port -a -t ssh_port_t -p tcp 2222
semanage port -l | grep ssh
```
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/9.PNG?raw=true)

```
systemctl daemon-reload (���sŪ���]�w��)
systemctl start sshd2.service (�}�� sshd2.service ���A��)
netstat -alntp | grep ssh
```
![image](https://github.com/bill0330/107-1-ntcu-linux/blob/HW-10/ACS107137/img/10.PNG?raw=true)