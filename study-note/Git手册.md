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

   
