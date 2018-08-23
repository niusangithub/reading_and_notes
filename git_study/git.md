## git笔记
>``` git reset HEAD```
>> 暂存区的目录树会被重写，被 master 分支指向的目录树所替换，但是工作区不受影响
#
>``` git rm --cached <file>```
>> 会直接从暂存区删除文件，工作区则不做出改变
#
>``` git checkout .  或者  git checkout --<file>```
>> 会用暂存区全部或指定的文件替换工作区的文件。这个操作很危险，会清除工作区中未添加到暂存区的改动。
#
> ```git checkout HEAD 或者 git checkout HEAD <file>```
>> HEAD 指向的 master 分支中的全部或者部分文件替换暂存区和以及工作区中的文件。清除工作区中未提交的改动，也会清除暂存区中未提交的改动

### git创建仓库
>```git init / git init newrepo ```
>>>``` git clone ```
>>>> 初始化
### git基本操作
>>``` git add *.c```
>>>``` git add README```
#
>>命令用于查看项目的当前状态。
>>>```git status ```
>>>>```git status -s 简短的输出```
#
>>> ``` git diff ```
>>>>git diff 命令显示已写入缓存与已修改但尚未写入缓存的改动的区别
>>>>>>git diff 尚未缓存的改动
>>>>>>git  diff --cached查看已缓存的改动
>>>>>>git diff HEAD 查看已缓存和未缓存的改动
>>>>>>git diff --stat 显示摘要而非整个diff
#
>>>>命令可将该文件添加到缓存
>>``` git commit -m '初始化项目'```
>>>``` git commit -am '跳过git add '```
#
>> ``` git rm <file> / git rm -f <file>```
>>>移除某个文件 / 如果已经放到缓存区
>>```git rm --cached <file>```
>> 把文件从缓存区移除，但仍希望保留在当前目录中
>>>```git rm –r * ```
>>>递归删除，即如果后面跟的是一个目录做为参数，则会递归删除整个目录中的所有子目录和文件
#
>>``` git mv```
>>>git mv 命令用于移动或重命名一个文件、目录、软连接。

### git分支管理
>>git branch 
>>>git创建分支
#
>>git checkout 
>>>git切换分支
#
>>git merge 
>>>合并分支
#
>> git checkout -b 
>>> 创建新的分支，并且立即切换到该分支下
#
>> git branch -d 
>>> 删除分支
#
>>>合并分支并且出现冲突，手动解决冲突后，用git add 告诉Git文件冲突已经解决了

### git查看提交历史
>>git log 
>>>git log --oneline
>>>>查看提交记录的简洁版
#
>>git log --oneline --graph
>>>查看历史中什么时候出现了分支、合并
#
>>git log --reverse --oneline
>>>用 '--reverse'参数来逆向显示所有日志
#
>>git log --author=Linus --oneline -5
>>>只想查找指定用户的提交日志
#
>>git log --oneline --before={3.weeks.ago} --after={2010-04-18} --no-merges
>>>指定日期( Git 项目中三周前且在四月十八日之后的所有提交，我可以执行这个--no-merges 选项以隐藏合并提交)