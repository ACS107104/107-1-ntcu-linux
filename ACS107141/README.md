# HW10

## �Х�ӽҰ�W�m�ߡA�z�Lsystemd�޲z�G��sshd�A�ȡA�����ĤG��sshd�A�Ȫ� port ���� 2222�C������i�H�ϥΫ��O `netstat -alntp | grep ssh`�T�{�O�_�ҰʤG��sshd�A�ȡC

    $ netstat -alntp | grep ssh
    tcp        0      0 0.0.0.0:22     0.0.0.0:*         LISTEN      1300/sshd
    tcp        0      0 0.0.0.0:2222   0.0.0.0:*         LISTEN      15275/sshd
    tcp6       0      0 :::22          :::*              LISTEN      1300/sshd
    tcp6       0      0 :::2222        :::*              LISTEN      15275/sshd
    
    Note 1: CentOS���ϥ�SELinux �A�G�w�]�u���\ SSH �ϥΰ� 22�A�Y�n�ϥΰ� 2222�A�ϽХΤU�C
            ���}�Ҩ��ˬd

    sh
    $ semanage port -a -t ssh_port_t -p tcp 2222
    $ semanage port -l | grep ssh
    ssh_port_t tcp 2202, 22
 

    Note 2: CentOS�w�]��������firewalld�|�T��X�ݰ�2222�A�Y�n�z�L2222��sssh�A�Х�����
    firewalld
--- 
* ��J<b>`systemctl stop firewalld`</b>����������(�����H���U�@)
![](https://i.imgur.com/EPccK5A.png)


* ��J<b>`systemctl status sshd.service`</b>�ˬd�ثe<b>`sshd.service`</b>���A
![](https://i.imgur.com/t1WYGxh.png)


* ��J<b>`cd /etc/ssh`</b>�i�J<b>`/etc/ssh`</b>��
![](https://i.imgur.com/907w41P.png)


* ��J<b>`cp sshd_config sshd2_config`</b>�ƻs<b>`sshd_config`</b>��<b>`sshd2_config`</b>
![](https://i.imgur.com/8D8PEOl.png)


* ��J<b>`vi sshd2_config`</b>�i�J�s��Ҧ�
![](https://i.imgur.com/WAoHSVU.png)
    > ���Ua,i,o�}�l�s��


* �N<b>`#Port 22`</b>�令<b>`Port 2222`</b>
![](https://i.imgur.com/OjHaxEF.png)
    > ���Uesc�ÿ�J`:wq`�x�s

* ��J<b>`cd /etc/systemd/system`</b>������<b>`/etc/systemd/system`</b>
![](https://i.imgur.com/oZDNbn0.png)

* ��J<b>`cp /usr/lib/systemd/system/sshd.service sshd2.service`</b>�N<b>`sshd.service`</b>�����e�ƻs��<b>`sshd2.service`</b>
![](https://i.imgur.com/KeyykQ9.png)

* ��J<b>`vi sshd2.service`</b>�i�J�s��Ҧ�
![](https://i.imgur.com/o2Xdhs1.png)
    >���Ua,i,o�}�l�s��

* <b>`Description=OpenSSH server daemon`</b>�᭱�[�W�@��<b>`2`</b>
    <b>`ExecStart=/usr/sbin/sshd -D $OPTIONS`</b>�����[�J<b>`-f /etc/ssh/sshd2_config`</b>
![](https://i.imgur.com/hylpC8T.png)
    >���Uesc�ÿ�J`:wq`�x�s

* ��J<b>`systemctl daemon-reload`</b>���sŪ���]�w��
    ��J<b>`systemctl enable sshd2`</b>�]�w���ҫ�Asshd2�|�Q�Ұ�
    ��J<b>`systemctl start sshd2`</b>�Ұ�sshd2
![](https://i.imgur.com/w2fVcN1.png)
    ><font color="#dd0000"><b>��������������������������������������������������������FAILED��������������������������������������������������������</b></font>

* ��J<b>`yum install policycoreutils-python`</b>
    ��J<b>`yum provides semanage`</b>�w��semanage���M��
![](https://i.imgur.com/QkSYLkk.png)

* ��J<b>`semanage port -a -t ssh_port_t -p tcp 2222`</b>
    ��J<b>`semanage port -l | grep ssh`</b>�ˬd Port �O�_�� 2222
![](https://i.imgur.com/rLUaPXa.png)

* ��J<b>`systemctl start sshd2`</b>���s�Ұ�sshd2
![](https://i.imgur.com/GsO8rUn.png)

* ��J<b>`netstat -tlnp | grep ssh`</b>��<b>`netstat -alntp | grep ssh`</b>�T�{�O�_�����\�Ұʨ��sshd�A��![](https://i.imgur.com/MWnOvhd.png)

    # <font color=red size=72>���\�I�I�I�I�I</font>