#�Ш̻��������U�C�ާ@��������������������z�L�����ۤ����q�G

##�bVirtalBox���إߤ@�ӷs��Host-only �����d�A���q��192.168.100.1/24

*�i�Jvirtuallbox�I��k�W������u����I��D�������޲z�����I��إߡ��b��} ��J192.168.100.1;�����B�n ��J255.255.255.0�������ҥΧY�i����

![image]()

##�إߵ�������-1�A�ñҥ�host-only�����d�A�z�Lifconfig �� ip���O�A�]�w��������-1��������192.168.100.100/24

*���U��ifconfig

>��Jyum install net-tools

*��Jip address add 192.168.100.100/24 broadcast + dev enp0s8

##�إߵ�������-2�A�ñҥ�host-only�����d�A�z�Lifconfig �� ip���O�A�]�w��������-2��������192.168.100.200/24

*��Jip address add 192.168.100.200/24 broadcast + dev enp0s8

![image]()

##�N�G�x���������������]�w�s��/etc/sysconfig/network-scripts/�U�۹�����ifcfg-*�ɮסA���s�Ұʵ��������A�T�{����ip�]�w�L�~�C

*�}�ҵ�������1

*��Jvi /etc/sysconfig/network-scripts/ifcfg-enp0s3

*��Ja

>�ҥνs��

*��ONBOOT=no�令yes

>�}���ɧY�|�۰ʶ}��

*IPADDR=192.168.100.100

>�s�W����IP��}

*��esc��:wq

>�x�s���}

![image]()

*�}�ҵ�������2

*��Jvi /etc/sysconfig/network-scripts/ifcfg-enp0s3

*��Ja

>�ҥνs��

*��ONBOOT=no�令yes

>�}���ɧY�|�۰ʶ}��

*IPADDR=192.168.100.200

>�s�W����IP��}

*��esc��:wq

>�x�s���}

![image]()

##�q��������-1 ping ��������-2�T�{�����O�s�q�A�ñq��������-2 ping ��������-1�A�T�{�����]�O�s�q�C

*���s�}�ҵ�������1

*��Jping 192.168.100.200

>�T�{����������G�������s�q

![image]()

*���s�}�ҵ�������2

*��Jping 192.168.100.100

>�T�{����������@�������s�q

![image]()
