#apache log�Oapache web server����x��

##�Ьd�� curl �� wget ���Ϊk��A�Ψ䤤�@�ӫ��O�U������x�ɡC


*��Jcurl https://raw.githubusercontent.com/ogre0403/107-1-ntcu-linux/master/resource/web.log

>�U����x��

![image]()

##�ϥ�bash��pipe���O�A�Ҧpgrep�Bcat...�����A�N����x��error�o�ͪ���]��X�ܿù��A����L��T���ݭn�e�{�C

*��Jcat web.log | grep error

>�u���x��error�o�ͪ���]��X�ܿù�

![image]()

#tar�Olinux�U�Ψӥ��]���Y�ؿ����u��A�Цۦ�d��tar���Ϊk��A�Τ@��ϥΪ̨������]�����Y/var�ؿ��C�btar����L�{���A�������`��X���G�A���ݱN���~�T����X��tar-err.log�ɮסC

*��Jtar -jcv -f filename.tar.bz2 /var 2> tar-err.log

>tar -jcv -f filename.tar.bz2�Ψ����Y�A/var�ɮצW�١A2> tar-err.log����~�T����X��tar-err.log��

*��Jcat tar-err.log

>����ɮפ��e

![image]()