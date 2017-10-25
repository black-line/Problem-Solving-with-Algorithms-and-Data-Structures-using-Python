website: [Problem Solving with Algorithms and Data Structures using Python](http://interactivepython.org/runestone/static/pythonds/index.html)

##### git commands:

---

基础

> `git add <file>`

> `git commit -m "message"`

> `git status`查看工作区的状态

管理修改

> `git diff <file>`是工作区和暂存区的对比;当暂存区中没有文件时,比较工作区中的文件与上次提交到版本库中的文件

> `git diff -- cached`是暂存区和分支的对比,查看已暂存的将要添加到下次提交里的内容

> `git diff HEAD -- <file>`比较工作区中的文件与版本库中文件的差异,HEAD指向版本库中的当前版本,<file>指的是当前工作区中的文件

版本回退

> `git log --pretty=oneline`查看提交历史/确定要回退到哪个版本号

>  `git reset --hard commit_id`版本回退或前进

>  `git reflog`查看命令历史/确定要回到未来的哪个版本

撤销修改

> `git checkout -- <file>`,撤销工作区中文件的修改;`git reset HEAD <file>`,撤销的是暂存区中文件的修改

> `git checkout -- <file>`有两种情况:
一种是<file>自修改后还没有被放到暂存区,现在,撤销修改就回到和版本库一模一样的状态;
一种是<file>已经添加到暂存区后,又作了修改,现在,撤销修改就回到添加到暂存区后的状态

> 场景1：当你改乱了工作区某个文件的内容,想直接丢弃工作区的修改时,用命令`git checkout -- <file>`

> 场景2：当你不但改乱了工作区某个文件的内容,还添加到了暂存区时,想丢弃修改,分两步,第一步用命令`git reset HEAD <file>`,就回到了场景1,第二步按场景1操作

> 场景3：已经提交了不合适的修改到版本库时,想要撤销本次提交,参考版本回退,不过前提是没有推送到远程库

删除文件

> `rm <file>`工作区删除有两种情况:
一种是误删,那么`git checkout -- <file>`,撤销删除,实际上删除也可以看做是对文件的一种修改;
一种是确实要删除,那么`git rm <file>`并且`git commit`

> 如果只想删除版本库中的某个文件,而仍想保留工作目录中的这个文件时,可以使用`git rm --cached <file>`
