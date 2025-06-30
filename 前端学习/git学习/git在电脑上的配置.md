# 关于在mac电脑上多git账号的配置
1. 先重置一下系统里面的用户名还有邮箱
git config --global --unset user.name
git config --global --unset user.email

2. 配置全局的用户名和邮箱
# 配置全局用户名，如Github上注册的用户名
git config --global user.name "xxx"  
# 配置全局邮箱，如Github上配置的邮箱  
git config --global user.email "yyy@mail.com"    

3. 最好是先检查一下自己有没有配置上
git config --global user.name
git config --global user.email

4. 创建ssh密钥
首先进入保存秘钥的目录，该目录下保存秘钥，需要提醒的是这个目录是默认隐藏的，可以打开Finder（访达），同时按下command + shift + .即可显示全部隐藏文件
# 查看秘钥目录
cd ~/.ssh 
# 创建秘钥（邮箱是你git上的邮箱）
ssh-keygen -t rsa -C "your_email@example.com"
# 查看公钥， id_rsa 没有pub 后缀的是秘钥，也叫私钥
cat ~/.ssh/id_rsa.pub 

5. 添加公钥
然后登陆github，进入setting，找到SSH and GPG keys，点击New SSH key，将上面生成的公钥复制进去，然后保存。

6. 结束，成功配置
// end at 6月30日
