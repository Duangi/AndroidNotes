## git fetch/pull

### 使用情况：

在修改完代码之后，发现队友已经提交commit了。

### 区别

git pull = git fetch + git merge

pull是将远程仓库的东西fetch到本地，再自动帮用户执行merge合并

### 冲突

如果你修改的文件和fetch下来的文件 不存在冲突的话，会被系统自动merge。在merge的过程中有可能会发生冲突。

此时需要git diff 查看区别，手动将冲突的文件修改正确。

### 重新合并

保留本地的更改,中止合并->重新合并->重新拉取

1. $:git merge --abort
2. $:git reset --merge
3. $:git pull

### 填写merge信息

成功进行git pull之后，也就是此时完成了一次merge操作，系统会询问你为什么要进行这次merge，它会自动打开一个文档编辑器，让你将信息填写在里面，类似于 git commit -m "" 所填写的信息

可能报错：hint:Waiting for your editor to close the file… 

原因分析：系统没有成功打开你的文档编辑器

解决方法：git config --global core.editor vim 修改文档编辑器为默认的vim



可能报错：

fatal: You have not concluded your merge (MERGE_HEAD exists).
Please, commit your changes before you merge.

解决方法：执行上面说的重新合并操作