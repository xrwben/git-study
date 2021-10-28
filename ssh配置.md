### window下如何配置ssh

1、打开git bash, 执行`cd ~/.ssh`命令切换到该目录下（C:\用户\LiBen\.ssh\）

2、使用`ls`命令查看电脑本地是否已配置ssh

3、执行生成公钥和私钥的命令`ssh-keygen -t rsa`, 回车确认信息，会生成三个文件（id_rsa、id_rsa.pub、known_hosts）

4、`cat id_rsa.pub`命令或使用文本编辑器打开 id_rsa.pub 文件并复制使用

5、到代码仓库找到设置SSH配置, 然后添加复制的id_rsa.pub公钥