##HW-3

<ol>
<ls>��J"ls -ali /etc/hosts"</ls>
![](https://i.imgur.com/u03xGHq.png)
>�̫e�����Ʀr��inode
>1���ɦW�b�ϥ�</ls> 
</ol>

<ol>
<ls>��J"ln /etc/hosts /srv/hosts.hard"�إ߹���s��</ls>
<ls>��J"ls -ali /srv/hosts.hard"</ls>
![](https://i.imgur.com/AAzOcjO.png)
>�̫e�����Ʀr��inode
>2���ɦW�b�ϥ�</ls>
*/etc/hosts�M�إߪ�����s��/srv/hosts.hard���b�ϥΡA�ҥH������ɦW
</ol>

<ol>
<ls>��J"ln -s /etc/hosts /srv/hosts.soft"�إ߲Ÿ��s��</ls>
<ls>��J"ls -ali /srv/hosts.soft"</ls>
![](https://i.imgur.com/n2NKr6b.png)
>�̫e�����Ʀr��inode
*�Ÿ��s�����W�ߪ��ɮסA�ҥH���|������s���@�˦@�ΦP�@��inode
</ol> 
