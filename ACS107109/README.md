# HW10
-------------------------------------
## �Х�ӽҰ�W�m�ߡA�z�Lsystemd�޲z�G��sshd�A�ȡA�����ĤG��sshd�A�Ȫ� port ���� 2222�C������i�H�ϥΫ��O` netstat -alntp | grep ssh `�T�{�O�_�ҰʤG��sshd�A�ȡC
* �ˬd�ثesshd.service�����A
 > systemctl status sshd.service

![image](01)


* �d��ExecStart:��ڰ��榹daemon�����O�θ}���{��
 > cat /usr/lib/systemd/system/sshd.service

![image](02)


* ������ssh���ؿ�
 > cd /etc/ssh

* �Nsshd_config����ƽƻs��sshd2_config
 > cp sshd_config sshd_config

* �s��sshd2_config�������(**�ק�Port��2222**)
  * **�`�N!!�n�NPort 2222�e�����r���R��!!���M�b�᭱�nstart sshd2�ɷ|�����D!!**
 > vim sshd2_config

![image](03)


![image](04)


* ������system���ؿ��U
  > cd /etc/systemd/system

* �N/usr/lib/systemd/system/sshd.service�����e�ƻs��sshd2.service
  > cp /usr/lib/systemd/system/sshd.service sshd2.service

* �s��sshd2.service�������
  > vim sshd2.service

![image](05)


* �ק�䤤��Description�C�A�b�̫᭱�[�W**2**
  > �]���O�t�@��daemon�A�ȡA�ҥH�n�N�qsshd�ƻs�L�Ӫ��ɮ׭קﱼ��!(���M�|�����D)

* �٦��ק��ExecStart:�л\���e�w�]�m��/usr/sbin/sshd
  > ExecStart=/usr/sbin/sshd **-f /etc/ssh/sshd2_config** -D $OPTIONS

![image](06)


* ���sŪ���]�w��(�ק�᳣�n����)
  > systemctl daemon-reload

* �]�w�U���}���ɡAsshd2�|�Q�Ұ�
  > systemctl enable sshd2

* �ߨ�Ұ�sshd2
  > systemctl start sshd2

  > ���|�o�{�OFailed�����D�A���L�A�O��ߡA���۰��᭱���B�J�o�Ӱ��D�N�|�Q�ѨM�o!

![image](07)

* �Q��**tail**�C�X�᭱�X�檺��T
  > tail -n 20 /var/log/messages

  > -n munber:��ܫD�Q�檺��T(����w�]�O��ܤQ��A���n��ܫD�ɦ檺��T�n�[�W` -n number `���ﶵ)

  > /var/log/messages�H�ɷ|����Ƽg�J�A�ҥH�i��ݷs�[�J�����

![image](08)

![image](09)

* �A�ӥ��w��` semanage `���M��A�H�Q���᪺�B�J�i��C
  > yum install policycoreutils-python

![image](10)

    > �ѨMsemanage command not found�����D�C
      >  https://www.opencli.com/linux/fix-semanage-command-not-found 

    > semanage �O�i�H�]�w SELinux ���u��A�b RHEL / CentOS minimal �w�˫�A�èS���w�� semanage�A�ҥH����|�X�{ command not found
  
  > �O�o�n������D�ؿ��U����A���M�|���ڤ@�}�l�@�˷|�����D(�o�O�w�˥��Ѫ��e��!)
![image](11)

  > �o�O���\�w�˪��e��!
![image](12)

* �� ssh �A�Ȩϥ�` 2222 `�o�Ӧۭq���s���𸹡A�N�o�ӳs���𸹥[�J` ssh_port_t `�C��
  > semanage port -a -t ssh_port_t -p tcp 2222

* �ߨ�Ұ�sshd2(�o���N���|�����D�o�A�H�W���B�J�H�ѨM���e���~������)
  > systemctl start sshd2

  > �ѩ�@�}�l��port�s���𸹩|���s�����\�A�ҥH�~���|�Ұʦ��\����!

* �T�{�O�_���Ұʨ��sshd�A��
  > netstat -tlnp | grep ssh

![image](13)


* netstat -tlnp | grep ssh�Mnetstat -alntp | grep ssh�|��ܤ@�˪����e��T

![image](14)