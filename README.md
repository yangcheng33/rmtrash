> rmtrash 是linux和mac下命令行版本rm的回收站，安装后对用户透明，符合正常使用rm的习惯(支持rm -rf file)，有了它再也不怕rm时候手颤抖了(能自动拒绝 rm -rf / 哦)。
> 
> rmtrash stands for "rm trash" which acts just like the system built-in rm command,and just moves the file to the trash for recovery when needed.


# 使用说明
## 1.安装
``` shell
wget --no-check-certificate https://raw.githubusercontent.com/yangcheng33/rmtrash/master/rmtrash.sh
sudo mkdir rmdir
sudo mv rmtrash.sh /rmdir/
sudo chmod +x /rmdir/rmtrash.sh
```
a. 如果仅对单个用户启用回收站，只需第一次执行如下命令即可:

``` shell
/rmdir/rmtrash.sh
source ~/.bashrc
```

b. 如果想对全局所有用户启用回收站，需要修改bashrc全局配置文件后即可：

``` shell
echo "alias rm=/rmdir/rmtrash.sh" >> /etc/bashrc
source /etc/bashrc
```

## 2.使用
```
rm -h
Usage1: rmtrash.sh file1 [file2] [dir3] [....] delete the files or dirs,and mv them to the rmtrash recycle rmdir
Usage2: rm         file1 [file2] [dir3] [....] delete the files or dirs,and mv them to the rmtrash recycle rmdir
        rm is alias to rmtrash.sh.
options:
	-f  mv one or more files to the rmtrash recycle rmdir
	-r  mv one or more files to the rmtrash recycle rmdir
	-fr mv one or more files to the rmtrash recycle rmdir
	-rf mv one or more files to the rmtrash recycle rmdir
	-R  Restore selected files to the originalpath from rmtrash recycle rmdir
	-l  list the contens of rmtrash recycle rmdir
	-i  show detailed log of the deleted file history
	-d  delete one or more files by user's input file name from the trash
	-e  empty the rmtrash recycle rmdir
	-h  display this help menu
```

如果有问题，执行以下命令排查，或者退出重新登录系统

`alias | grep rm`

## 3.彻底删除文件
1. `rm -e` 清空回收站
2. `/bin/rm file` 直接删除文件而不经过回收站


> 本脚本适用于linux、mac osx系统

