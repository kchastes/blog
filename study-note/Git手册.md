> 可以使用`git help <verb>`，`git <verb> --help`获取帮助，使用`git xxx -h`获得简短说明。

# 1. 配置

> 主要是针对`git config`命令

1. 查看配置文件所有选项和所在文件

   ```shell
   git config --list --show-origin
   ```

2. 设置用户信息

   ```shell
   # 只需配置一次，如果需要不同的，在不同项目下去掉--global选项即可
   git config --global user.name "XXX"
   git config --global user.email "XXX@email.com"
   ```

3. 设置默认编辑器

   ```shell
    # 在Windows下需要指定可执行文件路径地址
    git config --global core.editor emacs
   ```

4. 查看指定的属性的配置值

   ```shell
   git config xxx.xxx
   ```

5. 查看哪个文件最后修改的该属性

   ```shell
    git config --show-origin xxx.xxx
   ```

# 2.初始化

已跟踪的文件就是 `Git` 已经知道的文件，初次克隆某个仓库的时候，工作目录中的所有文件都属于已跟踪文件，并处于未修改状态。对已修改的文件，`Git`将标记为已修改，然后可以选择性的将这些文件放入暂存区(`add`)。

1. 初始化仓库

   ```shell
   # 在指定目录使用如下命令
   git init
   # 从远程下载
   git clone url <自定义名称>
   ```

2. 查看文件状态

   ```shell
   git status
   # 简短输出，有两栏，左栏暂存区，右栏工作区
   # A 表示新添加到暂存区的文件 ?? 为未跟踪文件 M 表示修改过的文件 例如：[AM] 表示已暂存，已修改， [A ]表示已暂存未修改
   -s 
   ```

3. 将文件设置为已追踪

   ```shell
   # 已追踪的会进入暂存状态，如果fileName是路径名，则会递归该路径下的所有文件
   # add命令就是将文件放入暂存区，还能将有冲突的文件标识为以解决状态
   # 精确地将内容添加到下一次提交中 表明该内容下一次需要进行提交
   git add <fileName>
   ```

4. 忽略文件

   ```shell
   # 通过创建.gitignore文件进行配置需要忽略的文件
   ```

5. 对比文件不同

   ```shell
   # 查看未暂存文件的不同 diff只显示尚未暂存的改动
   git diff
   # 查看已暂存文件和最后一次提交的文件差异
   --staged
   ```

6. 提交

   ```shell
   # 使用-v会显示出内容差异 -m直接添加提交注释 
   # 提交记录的是放在暂存区域的快照， 每一次运行提交操作，都是对你项目作一次快照
   # -a会提交所有修改过的文件
   git commit
   ```

7. 移除文件

   ```shell
   # 从已跟踪文件清单中移除 先手工删除，再执行git rm，下一次提交时，该文件就不再纳入版本管理了
   # 对于已经在暂存区中的文件，需要加上-f选项 注意会删除文件
   git rm
   # 第二种情况就是你想在磁盘保留，但是不想被git追踪
   # 使用--cached选项
   ```

8. 移动文件

   ```shell
   git mv
   # 相当于执行了三条命令
   mv README.md README
   git rm README.md
   git add README
   ```

# 3. 历史

1. 查看提交记录

   ```shell
   git log
   # -p 显示出每次的差异 --stat 总结性的显示 --graph以分支图的方式显示 -n 表示数字，查看n条
   ```

2. 撤销操作

   ```shell
   # 替换暂存区中的文件提交，如果没有做任何修改，那只会改变提交信息。
   git commit --amend
   
   ```

# 4. 远程

1. 查看远程地址

   ```shell
   git remote # -v 显示列表
   ```

2. 添加远程仓库

   ```shell
   git remote add <shortName> <url>
   ```

3. 访问

   ```shell
   # 拉下所有你还没有的数据，但是不会自动合并
   git fetch <remote>
   ```

4. 推送到远程

   ```shell
   git push <remote> <branch>
   ```

   

