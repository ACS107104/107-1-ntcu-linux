1.
rpm -ql openssh-server
�Ϥ@

systemctl status sshd.service
systemctl status sshd.socket
�ϤG

vi /etc/ssh/sshd_config
�ϤT

semanage port -a -t ssh_port_t -p tcp 2222
�ϥ|

firewall-cmd --permanent --zone=public --add-port=2222/tcp
�Ϥ�

systemctl restart sshd.service
�Ϥ�

ss -tnlp | grep sshd
�ϤC

