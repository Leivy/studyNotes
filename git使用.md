### git使用

+ git add -A;git commit -m "tag";git push origin master;-->联网推送到GitHub远程仓库


+ 一些git bash命令:

  + git init:初始化一个git仓库

  + git add readme.txt:添加文件修改到暂存区,就是.git下的index(或者叫做stage),不add放入暂存区的修改都不会提交到分支,git add -A;提交当前仓库所有文件到暂存区

  + git status:查看仓库当前状态

  + git diff: 查看修改了什么内容

    + git commit -m "add readme.txt":把暂存区的所有内容提交到当前分支master

  + cat readme.txt:查看文件内容

  + git log:查看修改的历史记录,如果嫌输出信息太多，看得眼花缭乱的，可以试试加上`--pretty=oneline`参数：$ git log --pretty=oneline

  +  版本回退:git reset命令:$ git reset --hard HEAD^ ,回退到上个,HEAD^^回退到上上个,回退到100个,HEAD~100,HEAD指向的版本就是当前版本

  + git reflog:查看每一次的命令,可以版本穿梭,

  + 隐藏目录.git是Git的版本库

  + git checkout --readme.txt:把工作区的readme.txt文件修改全部清空,

  + git reset HEAD readme.txt:可以把暂存区的修改撤销掉（unstage），重新放回工作区：

    + ```tex
      场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。

      场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD file，就回到了场景1，第二步按场景1操作。

      场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。
      ```

  + git push -u origin master:第一次推送到远程仓库,后续用新的命令:$ git push origin master

  + 分支

    + Git鼓励大量使用分支：

      查看分支：`git branch`

      创建分支：`git branch <name>`

      切换分支：`git checkout <name>`

      创建+切换分支：`git checkout -b <name>`

      合并某分支到当前分支：`git merge <name>`

      删除分支：`git branch -d <name>`