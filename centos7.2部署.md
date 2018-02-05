### 修改hostname

vim /etc/hostname  重启后生效

### 新增用户

adduser wangfeiyang

passwd wangfeiyang

gpasswd -a wangfeiyang wheel（只有属于wheel组的用户才可以用su登录为root）

