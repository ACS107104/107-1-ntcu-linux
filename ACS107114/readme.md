## HW10
#### �Х�ӽҰ�W�m�ߡA�z�Lsystemd�޲z�G��sshd�A�ȡA�����ĤG��sshd�A�Ȫ� port ���� 2222�C������i�H�ϥΫ��O netstat -alntp | grep ssh �T�{�O�_�ҰʤG��sshd�A��

* ���ϥ�`cd /etc/ssh/`�i�J��Ƨ��A�A�ϥ�`cp sshd_config sshd2_config`�ƻs�ɮ�

![](https://i.imgur.com/BY7ymbf.jpg)

* ��`vi sshd2_config`�i�J�s��Ҧ��A�N���e**port22**�אּ**Port 2222**
![](https://i.imgur.com/bS3UWFK.jpg)

* ���ۿ�J`cd /usr/lib/systemd/system`���**sshd.service**
![](https://i.imgur.com/wX3yI7Y.png)

* �ñN��ƻs��`/etc/systemd/system`
![](https://i.imgur.com/xVksodq.png)

* ���̨ϥ�`vi`�s����ɮ�
![](https://i.imgur.com/uNSSmID.jpg)

* �]���̫�ϥΪ����O�ݭn�w�ˤ@�װt��A�G�b�o�̭n����J`yum provides semanage`u�H��`yum install policycoreutils-python`
![](https://i.imgur.com/5rxA7Up.png)

* �̫�ϥ�`systemctl stop firewalld.service`����������A�A��J`systemctl daemon-reload`�A�H��`systemctl start sshd2`�A�̫᪺�̫�ϥ�`netstat -alntp | grep ssh`�ˬd�O�_���\

![](https://i.imgur.com/hbxNT66.png)


![](https://i.imgur.com/UgkxV5l.jpg)