## 1、Git 版本

查看版本：

```git
git --version
```

## 2、Git 的使用

### 2.1 Git 使用前配置

1. 配置提交人姓名：

   ```git
   git config --global user.name 提交人姓名
   ```

2. 配置提交人邮箱：

   ```git
   git config --global user.email 提交人邮箱
   ```

3. 查看git配置信息：

   ```git
   git config --list
   ```

### 2.2 提交步骤

1. 初始化git仓库：

   ```git
   git init
   ```

2. 查看文件状态：

   ```git
   git status
   ```

3. 追踪文件：

   ```git
   git add 文件列表
   ```

4. 向仓库中提交代码：

   ```git
   git commit -m 提交信息
   ```

5. 查看提交记录：

   ```git
   git log
   ```

### 2.3 撤销
- 用暂存区中的文件覆盖工作目录中的文件：

  ```git
  git checkout 文件名
  ```

- 将文件从暂存区中删除：

  ```git
  git rm --cached 文件名
  ```

- 将git仓库中指定的更新记录恢复出来，并且覆盖暂存区和工作目录： 

  ```git
  git reset --hard commitID
  ```

![image-20200712191137295](C:\Users\djf24\AppData\Roaming\Typora\typora-user-images\image-20200712191137295.png)

## 3、 Git 进阶

### 3.1 Git 分支

1. 主分支（master)：第一次向 git 仓库中提交更新记录是自动产生的一个分支。
2. 开发分支（develop）：作为开发的分支，基于 master 分支创建。
3. 功能分支（feature）：作为开发具体功能的分支，基于开发分支创建。

### 3.2 分支命令

- 查看分支：

  ```git
  git branch
  ```

- 创建分支：

  ```git
  git branch 分支名称
  ```

- 切换分支：

  ```git
  git checkout 分支名称
  ```

- 合并分支：

  ```git
  git merge 来源分支
  ```

- 删除分支（分支被合并后才允许删除）（-D 强制删除）：

  ```git
  git branch -d 分支名称
  ```

### 3.3 暂时保存更改

- 存储临时改动：

  ```git
  git stash
  ```

- 恢复改动：

  ```git
  git stash pop
  ```
  
## 4、Git 远程仓库

1. 向远程仓库推送本地仓库：`git push 远程仓库地址 分支名称`。例：

   ```
   git push https://github.com/zhangsan/test.git master
   ```

2. 给远程仓库取个简单的别名（常用第一步骤）：`git remote add 远程仓库地址别名 远程仓库地址`。例：

   ```
   git remote add origin|test https://github.com/zhangsan/test.git 
   ```

3. 给远程仓库取个简单的别名：`git push 远程仓库地址别名 分支名称`。例：

   ```
   git push origin|test master
   ```

4. 让git记住地址与分支（-u 记住推送地址与分支，下次推送只需要输入 `git push` 即可）（常用第二步骤）：`git push -u 远程仓库地址别名 分支名称`

   ```
   git push -u origin|test master
   ```

   