# HW-10
---
## �Х�ӽҰ�W�m�ߡA�z�Lsystemd�޲z�G��sshd�A�ȡA�����ĤG��sshd�A�Ȫ� port ���� 2222�C������i�H�ϥΫ��O netstat -alntp | grep ssh �T�{�O�_�ҰʤG��sshd�A�ȡC
### �ϥ�cp�ƻssshd_config��sshd2_config
![](https://i.imgur.com/7nytye7.png)
### ��vi�i�Jsshd2_config�ñNport 22�אּport 2222
![](https://i.imgur.com/prN0VcK.png)
### ��cp�ƻscp /usr/lib/systemd/system/sshd.service ��sshd2.service
![](https://i.imgur.com/K8JXLCX.png)
### ��vi�Ntype�אּsimple�B�NExecStart�令/usr/sbin/sshd -f /etc/ssh/sshd2_config -D
![](https://i.imgur.com/X3cApR3.png)
### ��yum�U�����O�]
![](https://i.imgur.com/uC1OcRz.png)
![](https://i.imgur.com/iIKabOP.png)
### ��semanage port -a -t ssh_port_t -p tcp 2222�]�w,�M���semanage port -l | grep ssh�T�{
![](https://i.imgur.com/3qy4VRv.png)
### ��systemctl daemon-reload�Msystemctl start sshd2.service���s�Ұ�sshd2_service
![](https://i.imgur.com/kqM4nHD.png)
### �̫��netstat -alntp | grep ssh�d��