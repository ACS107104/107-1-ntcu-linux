##1

1. 
```
#ver=$(uname -r)
``` 
2.
```
#echo $ver
``` 
*���3.10.0-862.e17.x86_64
3.
```
#ver="my kernel version is 3.10"
```
4.(�ˬd)
```
#echo $ver
```
*�X�{my kernel version is 3.10

*![](https://i.imgur.com/nfNcAVQ.png)
*�@�~�t�η|�̷�PATH�����ܼƤ��ҳ]�w�����|���ǡA�̧ǴM��U���|�U�O�_���o�ӫ��O�C

##2

*root�M�P�s�ժ��b���㦳rwx�v���A��L�b���h�u��rx�v��

1.
```
#chmod 777 ~/script.sh
```
2.
```
#chmod u=rwx,g=rwx,o=rwx ~/script.sh
```

##3

*����s���O�b�ؿ��̥[�@��inode�P�ɦW����
*�Ÿ��s���O�إ߿W���ɮ׫��V�ت��ɮ�

*����s��
1.
```
#ll -i /etc/hosts
``` 
2.
```
#ln /etc/hosts .
```
3.(�ˬd) 
```
ll -i /etc/hosts hosts.real
```

*�Ÿ��s��
1.
```
#ln -s /etc/hosts hosts.symbo
```
2.(�ˬd) 
```
#ll -i /etc/hosts /root/hosts.symbo
```

##4
*���Ҵ��ըt�Υ����}
