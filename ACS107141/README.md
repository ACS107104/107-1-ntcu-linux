##1 
#�إ߸s��
	<ol>
	<li>��Jgroupadd mygroup</li>
	<li>��Jgroupadd nogroup</li>
	<li>��Jgrep group /etc/group�T�{���S�����\�[�J</li>
	<li><p>��Juseradd -g mygroup myuser1</p>
		<p>��Juseradd -g mygroup myuser2</p>
		<p>��Juseradd -g mygroup myuser3</p>
		<p>��Juseradd -g nogroup nouser1</p>
		<p>��Juseradd -g nogroup nouser1</p>
		<p>��Juseradd -g nogroup nouser1</p></li>
	</ol>	
#�]�w�K�X(�Ҭ�MyPassWord)	
	<ol>
	<li><p>��Jpasswd myuser1</p>
		<p>��Jpasswd myuser2</p>
		<p>��Jpasswd myuser3</p>
		<p>��Jpasswd nouser1</p>
		<p>��Jpasswd nouser1</p>
		<p>��Jpasswd nouser1</p></li>
	</ol>	
#�ˬd�ϥΪ̬O�_�b���T���s�դ� 
	<ol>
	<li><p>��Jll /home/</p>
		<p>�����</p>
		<p>drwx------. 2	myuser1	mygroup	62 ���	�ɶ�	myuser1</p> 
		<p>drwx------. 2	myuser2	mygroup	62 ���	�ɶ�	myuser2</p>
		<p>drwx------. 2	myuser3	mygroup	62 ���	�ɶ�	myuser3</p> 
		<p>drwx------. 2	nouser1	nogroup	62 ���	�ɶ�	nouser1</p> 
		<p>drwx------. 2	nouser2	nogroup	62 ���	�ɶ�	nouser2</p> 
		<p>drwx------. 2	nouser3	nogroup	62 ���	�ɶ�	nouser3</p></li>
	</ol>	
#�إߥؿ�	 
	<ol>
	<li>��Jmkdir -m 070 /srv/myproject</li>
	<li>��Jchgrp mygroup /srv/myproject</li>
	<li><p>��Jll /srv</p>
		<p>���|���</p>
		<p>d---rwx---. 2	root	mygroup 6	���	�ɶ�	myproject</p></li>
	</ol>
#�n�Jmyuser1�ë��� 
	<ol>
	<li>��Jsu myuser1</li>
	<li>��Jcd /srv/myproject</li>
	<li>��Jtouch myuser1.data</li>
	<li><p>��Jll /srv/myproject</p>
		<p>�����</p>
		<p>-rw-r--r--. 1	myuser1	mygroup	0	���	�ɶ�	myuser1.data</li>
	<li>���^root��Jcp /usr/bin/ls /user/local/bin/myls�ƻs�ɮ�</li>
	<li><p>��Jll /usr/local/bin</p>
		<p>�����</p>
		<p>-rwxr-xr-x. 1	root	root	117672	���	�ɶ�	myls</v></li>
	</ol>	
#�ק�u�v���Onouser1�i�ϥ�/srv/myproject		
	<ol>
	<li>��Jchmod u+s /usr/local/bin/myls</li>
	<li><p>��Jll /usr/local/bin/myls</p>
		<p>�����</p>
		<p>-rwsr-xr-x. 1	root	mygroup	117672	���	�ɶ�	/usr/local/bin/myls</li>
	</ol>
#������nouser1����		
	<ol>
	<li>��Jmyls /srv/myproject�X�{myuser1.data�Y���\</li>
	</ol> 

##2
#�ϥε{���[����O�A�f�t grep ������r�d�ߥ\��A�N��쪺 rsyslog �������{�Ǫ� PID, PRI, NI, COMMAND ����T��s�� /root/process_syslog.txt �ɮפ��C
	<ol>
	<li>��Jps aux |grep rsyslog</li>	
	<li>��Jps aux |grep rsyslog > /root/process_syslog.txt</li>
	<li>��Jcat/root/process_syslog.txt</li>
	![2] (2.png)
	</ol>
	
##3	
	<ol>
	<li>��Jtop</li>
	![3] (3.png)	
