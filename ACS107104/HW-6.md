#�Цb�a�ؿ��U��.bashrc�̷s�W�@��shell�ܼ� HOSTS_PATH=/etc/hosts�A(�`�N���ݥ�export)�A�����p�󤣵n�X��HOSTS_PATH�ܼƥͮġA����cat $HOST_PATH�T�{��Ū�����ɮפ��e�C

*��Jvi ~/.bashrc

>�s�W�ɮ�

*��Ji

>�ҥνs��

*��JHOSTS_PATH="/etc/hoats"

>�s�W�ܼ�

*��ESC���:wq

>�Y�i�x�s�����}

*��Jsource ~/.bashrc

>Ū���ҳ]�w�ɪ����O

![image]()

*��Jcat $HOSTS_PATH

>�d�ݦ��L���\

![image]()

---------------------------------------

#�bC�y���{���i�H��getenv()Ū��LINUX�������ܼơA�d�ҵ{���p�U�C�ЦbLinux�̽sĶ���d�ҵ{���ð���A�аݧ_��Ū��HOSTS_PATH�H��$?���Ȭ���A�л����C�]�\�ݳz�Lyum groupinstall "Development Tools"�w��gcc�C

*��Jyum groupinstall "Development Tools"

>�w��gcc

*��J'vi test.c'

>�s�W�ɮ�

*��Ji

>�ҥνs��

*��J�{��

![image]()

*��J'gcc test.c'

>�sĶ

*��J'./a.out'

>��X���G

*��J'echo $?'

>�L�X���e

![image]()

*�S��Ū��HOSTS_PATH

>�]�����'getenv() return NULL'

*$?���Ȭ�1

>���~

-----------------------------------
#�b.bashrc�̭n�p��ץ��A��C�y���{���i�HŪ�������ܼƨñN�ɮפ��e��ܡC

*��J'vi ~/.bashrc'

>�s��.bashrc

*��J'export HOSTS_PATH=/etc/hosts'

![image]()

*��J'source .bashrc'

*��J'gcc test.c'

>�sĶ

*��J'./a.out'

>��X���G

*��J'echo $?'

>�L�X���e

*��Ū��HOSTS_PATH

>�]�������HOSTS_PATH

*$?���Ȭ�0

>���T

![image]()