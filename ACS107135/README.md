## �Х�ӽҰ�W�m�ߡA�z�Lsystemd�޲z�G��sshd�A�ȡA�����ĤG��sshd�A�Ȫ�port����2222�C������i�H�ϥΫ��O`netstat -alntp | grep ssh`�T�{�O�_�ҰʤG��sshd�A�ȡA�d�Ҧp�U�G

```sh
$ netstat -alntp | grep ssh
tcp 0 0 0.0.0.0:22 0.0.0.0: *       LISTEN 1300/sshd
tcp 0 0 0.0.0.0:2222 0.0.0.0: *       LISTEN 15275/sshd
tcp6 0 0 :::22 ::: *            LISTEN 1300/sshd
tcp6 0 0 :::2222 ::: *            LISTEN 15275/sshd
```

 Note 1: CentOS���ϥ�SELinux �A�G�w�]�u���\ SSH �ϥΰ� 22�A�Y�n�ϥΰ� 2222�A�ϽХΤU�C���}�Ҩ��ˬd

    ```sh
    $ semanage port -a -t ssh_port_t -p tcp 2222
    $ semanage port -l | grep ssh
    ssh_port_t tcp 2202, 22
    ```  

    Note 2: CentOS�w�]��������firewalld�|�T��X�ݰ�2222�A�Y�n�z�L2222��sssh�A�Х�����firewalld�C

### `netstat -alntp | grep ssh` �T�{sshd�A��
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/1.PNG)</br></br>
### `yum provides semanage`�d��semanage����ӮM��
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/2.PNG)</br>
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/3.PNG)</br></br>
### `yum install policycoreutils-python`�w�ˤu��
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/4.PNG)</br></br>
### 
    ```sh
    $ semanage port -a -t ssh_port_t -p tcp 2222
    $ semanage port -l | grep ssh
    ssh_port_t tcp 2202, 22
    ```  
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/5.PNG)</br></br>
### `service firewalld stop` ����firewalld������
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/6.PNG)</br></br>
### �ƻssshd_config��sshd2_config
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/7.PNG)</br></br>
### �ק�`#Port 22`��`Port 2222`
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/8.PNG)</br></br>
### �ƻssshd.service��sshd2.service
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/9.PNG)</br></br>
### �ק�sshd2.service
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/10.PNG)</br></br>
### `systemctl daemon-reload`���sŪ���]�w
### `systemctl start sshd2.service`�ҥ�sshd2.service
### `netstat -alntp | grep ssh`�T�{�ĤG��sshd�A�Ȥw�Ұ�
![image](https://github.com/ACS107135/107-1-ntcu-linux/blob/HW-10/ACS107135/photo/11.PNG)</br></br>