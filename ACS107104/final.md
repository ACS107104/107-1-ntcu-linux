#�]�wvirtualbox���������A�[�J�@�ihost-only�����d�A�bLinux�̳]�w����������������192.168.200.100/24�C�Х� `ifconfig`���ҡC

*�i�Jvirtuallbox�I��k�W������u����I��D�������޲z�����I��إߡ��b��} ��J192.168.100.1;�����B�n ��J255.255.255.0�������ҥΧY�i����

*��Jip address add 192.168.200.100/24 broadcast + dev enp0s8

*��Jip addr(�]����Jifconfig�L�k�]�X�A�ҥH�Hip addr�N��)

![image](1)

#nginx�O�@�M�������A���n��A�Х�`yum`�w�ˡA�z�L`systemctl`�Ұʫ�A�ϥ�`netstat`����nginx���b�ϥ�Port 80�C

*sudo rpm -Uvh http://nginx.org/packages/centos/7/noarch/RPMS/nginx-release-centos-7-0.el7.ngx.noarch.rpm

*sudo yum install -y nginx

*sudo systemctl start nginx.service

![image](2)

#�z�L���� windows �W���s�����A�s�u��192.168.200.100�C��?�����ҥi�H�s�u��Linux�W��nginx�������A���C

*

![image](3)

#�bLinux�̡A��`curl`�s�u��192.168.200.100�C��?�����ҥi�H�s�u��Linux�W��nginx�������A���C

*curl 192.168.200.100

![image](4)

#nginx����x�ɦ��`/?var/log/nginx`�ؿ��U�A��s�u���s�b�������ɡAnginx�|�O��������T�A�榡�p�U�C�䤤client��쬰�Ȥ��ip�C

*