1. ��Jcd /etc/ssh�A�M���Jsshd*������ssh�A�ϥ�cp���O�Nsshd_config�ƻs��sshd2_config�C
![](https://i.imgur.com/ps2B6Rs.png)
2. ��Jvi sshd2_config �N#Port 22�令Port 2222
![](https://i.imgur.com/xebT5Ls.png)
![](https://i.imgur.com/wZpwtr4.png)
3. �ϥ�cp���O�Nsshd.service�ƻs��sshd2.service
![](https://i.imgur.com/o6TylDj.png)
4. vi ssh2.service�ק鷺�e
![](https://i.imgur.com/gWyqdtk.png)
5. ��Jyum provides semanage�d�߫��O
![](https://i.imgur.com/zRv54Qr.png)
![](https://i.imgur.com/RS93j3v.png)
6. ��Jyum install policycoreutils-python�w��semanage
![](https://i.imgur.com/zV3cGNT.png)
![](https://i.imgur.com/1rocupS.png)
7. ��Jsemanage port -a -t ssh_port_t -p tcp 2222 
![](https://i.imgur.com/rLpucEm.png)
8. ��Jsemanage port -l | grep ssh 
![](https://i.imgur.com/EwPip1a.png)
![](https://i.imgur.com/PGO1sLt.png)
9. ��Jnetstat -alntp | grep ssh
![](https://i.imgur.com/lwsxNcX.png)
![](https://i.imgur.com/rU1wdi5.png)
10. ����