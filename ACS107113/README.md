## HW10
#### �Х�ӽҰ�W�m�ߡA�z�Lsystemd�޲z�G��sshd�A�ȡA�����ĤG��sshd�A�Ȫ� port ���� 2222�C������i�H�ϥΫ��O netstat -alntp | grep ssh �T�{�O�_�ҰʤG��sshd�A�ȡC

+ systemctl status sshd �A�d��sshd�����A
![GITHUB]( https://imgur.com/55E9tRz.jpg"git�ϥ�")

+ �w��vsftpd�Ayum install vsftpd�C
![GITHUB]( https://imgur.com/BxZInaJ.jpg"git�ϥ�")

![GITHUB]( https://imgur.com/G7vhfFy.jpg"git�ϥ�")
+ �}�Ҥu��Ayum provides semanage�C
![GITHUB]( https://imgur.com/UAUta9G.jpg"git�ϥ�")

+ �w��policycoreutils-python�Ayum install policycoreutils-python�C
![GITHUB]( https://imgur.com/uHeJjPE.jpg"git�ϥ�")
![GITHUB]( https://imgur.com/2SJvF4D.jpg"git�ϥ�")

+ ������ؿ�cd /etc/ssh�C�ƻs�ɮסAcp sshd_config sshd2_config�C
![GITHUB]( https://imgur.com/FgH0M4P.jpg"git�ϥ�")

+ ��鷺�e�APort=22 -> Port=2222�Avi sshd2_config �C
![GITHUB]( https://imgur.com/UUzrHVv.jpg"git�ϥ�")

+ ������ؿ�cd /etc/systemd/system �C�ƻs�ɮסAcp /usr/lib/systemd/system/sshd.service sshd2.service�C
![GITHUB]( https://imgur.com/3BuEEwA.jpg"git�ϥ�")

+ ��鷺�e�Avi sshd2.service�C
![GITHUB]( https://imgur.com/SZfm1oc.jpg"git�ϥ�")

+ semanage port -a -t ssh_port_t -p tcp 2222�ץ��Csemanage port -l | grep ssh�d�ݡC
![GITHUB]( https://imgur.com/VMSDAx3.jpg"git�ϥ�")

+ systemctl daemon-reload�A���䭫�sŪ���A�Ұ�sshd2_service�Asystemctl start sshd2.service�C
![GITHUB]( https://imgur.com/Y92l5Ub.jpg"git�ϥ�")

+ netstat -alntp | grep ssh�A�d�ݵ��G�C