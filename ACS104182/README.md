<strong>�Ĥ@�j�D</strong><br>

����rpm -ql openssh-server���O�ݤ@�U��X <br>
![5](1.jpg)<br>

�z�L�H�U�R�O���O�T�{ sshd �A�ȬO�� .service ���ҰʡA�٬O�O�� .socket ���ҰʡG <br>
systemctl status sshd.service        ,    systemctl status sshd.socket
![5](2.jpg)<br>


���۳z�L���O��vim �ק��󤺮e��port�令2222:vi /etc/ssh/sshd_config
![5](3.jpg)<br>


��J�R�Osemanage port -a -t ssh_port_t -p tcp 2222 ���\�sport <br>
![5](5.jpg)<br>


��J�R�Ofirewall-cmd --permanent --zone=public --add-port=2222/tcp ��L������ <br>
![5](6.jpg)<br>



��J�R�O systemctl restart sshd.service���ҪA��<br>
![5](7.jpg)<br>



��J�R�Oss -tnlp | grep sshd �ݵ��G<br>
![5](8.jpg)<br>


