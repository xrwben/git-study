### window下如何配置ssh

1、打开git bash, 执行`cd ~/.ssh`命令切换到该目录下（C:\用户\LiBen\.ssh\）

2、使用`ls`命令查看电脑本地是否已配置ssh

3、执行生成公钥和私钥的命令`ssh-keygen -t rsa`, 回车确认信息，会生成三个文件（id_rsa、id_rsa.pub、known_hosts）

4、`cat id_rsa.pub`命令或使用文本编辑器打开 id_rsa.pub 文件并复制使用

5、到代码仓库找到设置SSH配置, 然后添加复制的id_rsa.pub公钥


### TortoiseGit工具

1、使用TortoiseGit工具pull或push时提示Disconnected: No supported authentication methods available (server sent: publickey)错误？

解决：在 git bash 中没有错误, 所以是TortoiseGit的配置问题, 需要设置下TortoiseGit的SSH配置, 找到 TortoiseGit -> Settings -> Network -> SSH client, 替换为Git安装目录下usr/bin/ssh.exe文件(或者bin/ssh.exe)即可
