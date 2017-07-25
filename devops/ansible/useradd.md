# ubuntu添加用户


#### 问题
在osx下 使用ansible新建用户的playbook example中的命令，python -c 'import crypt; print crypt.crypt("This is my Password", "$1$SomeSalt$")', 输出的字符串长度和示例中的不匹配
#### 原因
osx的密码加密方法与linux不一致
#### 解决方案
- 安装passlib： sudo pip install passlib
- 修改生成密码命令为： from passlib.hash import md5_crypt
python -c 'import crypt; print md5_crypt.encrypt("This is my Password,salt="SomeSalt")'
'$1$SomeSalt$UqddPX3r4kH3UL5jq5/ZI.'