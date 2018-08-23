### git笔记
> git reset HEAD
>> 暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响
#
> git rm --cached <file>
>> 会直接从暂存区删除文件，工作区则不做出改变
#
> git checkout .  或者  git checkout --<file>
>> 会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区的改动。
#
> git checkout HEAD 或者 git checkout HEAD <file>
>> HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。清除工作区中未提交的改动，也会清除暂存区中未提交的改动