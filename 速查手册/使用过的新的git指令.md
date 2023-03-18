# 使用过的新的git指令

* git diff 分支1 分支2 --stat 比较两个分支所以的区别
* git commit --amend       修改本次commit信息

## 一些功能
### 将远程库的某个分支拉取到本地的分支中  

 拉取远程某个指定分支可以使用：
 git clone -b 分支名 地址
 的方式，通过-b参数指定clone的分支
 
 在本地已有仓库的情况下，想要拉取某个远程库的某个分支到本地，这就稍微复杂一些
 
#### 分析：
     本地已有仓库，而且是拉取分支到本仓库中，所以不能使用clone指令了
     本地仓库已有一定的分支，拉取一条分支到这些分支群中，甚至可以不一定是本仓库的代码分支。
     在本地新建一个分支放置他，完全是新的内容，并不是本地已有分支创建出来后合并的，并且是任意分支都可以拉取下来
     拉取其他远程库的分支，到另一个仓库，甚至两个仓库代码没有一点相似性
 

#### 思路：
    将新分支fetch到本地，再以他为基础创建本地的新分支

     fetch指令
     作用是将代码下载到本地
     可以是整个仓库或者一个分支
     代码保存在某个地方，通过 “远程库/分支的方式获取

     使用指令：
     git fetch origin develop
     下载origin远程库的develop分支
     
     git fetch [地址] develop
     下载[地址]所在远程库的develop分支

     分支或引用下载后，可以使用 "远程库/分支名"的方式获取，必须是以"/"分隔，不要使用空格

     使用指令：
     git checkout -b develop origin/develop 
     将下载的分支设置为本地仓库的分支

#### 指令官方解释：
     fetch
          git fetch命令用于从另一个存储库下载对象和引用
          git fetch可以从单个命名的存储库或URL中获取，也可以从多个存储库中获取，如果给定了<group>，并且配置文件中有一个远程<group>条目。

     checkout
          git checkout命令用于切换分支或恢复工作树文件。
          更新工作树中的文件以匹配索引或指定树中的版本。如果没有给出路径 - git checkout还会更新HEAD，将指定的分支设置为当前分支。 


### git 撤销提交

     撤销暂存，撤销commit，撤销远程push

#### 撤销push到远程库的
     如果你想撤销一次push
     你可以把本地恢复到远程库的版本，添加--force参数push到远程库后，再撤销恢复达到撤销push的目的。
     且不远程库会留下commit记录

     git push ...
     之后

     本地回退版本，与之前远程库版本一致
     git reset --soft 版本号       // --soft 不清除工作区

     由于版本落后当前远程库，使用--force参数强制push
     git push --force...

     此时远程库已恢复到之前版本，且没有记录

     本地返回到之前版本
     git reset --soft 版本号       // --soft 同上

#### 指令分析
* reset   重置
* push    推送

### 暂时忽略
     短期的忽略提交某个文件

#### 描述
     .gitignore文件不能忽略已跟踪文件

     若想暂时性的短期内的不跟踪某个或某些文件
     可以使用： 指令 update-index

          --assume-unchanged  暂时忽略
          --no-assume-unchanged    取消暂时忽略

#### 注意：
     忽略后不能切换分支等，会提示有文件更改未提交。

#### 完整指令               
     git update-index --assume-unchanged 文件路径 暂时不跟踪某个文件
     git update-index --no-assume-unchanged 文件路径 取消暂时不跟踪某个文件
     
### 附录        

* git fetch 远程库 分支名  
     拉取远程库分支或引用
      
  示例: git fetch origin uat_czl1 
      
 * git checkout -b 本地分支或新分支 远程库/分支名  
     创建一个新的分支
     
     示例: git checkout -b uat_czl1 origin/uat_czl1
     
* git update-index --assume-unchanged 文件路径
     暂时不跟踪某个文件
     
     示例：git update-index --assume-unchanged vue.config.js
 
      