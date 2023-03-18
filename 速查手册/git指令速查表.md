# git指令速查表

## 分支
git branch -vv                    # 查看与远程分支对应情况
git branch -m oldName newName     # 分支重命名
git branch -d branchName          # 删除分支
git branch --unset-upstream       # 取消关联远程分支
git remote update origin --prune  # 刷新远程分支列表
git branch --set-upstream-to=origin/branchName              # 重新关联远程分支

## update-index
git update-index --assume-unchanged vue.config.js           # 暂时不跟踪某个文件
git update-index --no-assume-unchanged vue.config.js        # 取消暂时不跟踪某个文件

## 版本回退
git reset --hard HEAD^                  # 返回上一版本
git reset --hard HEAD~100               # 返回前一百版本
git reset --hard 1094adb                # 返回1094adb版本

## stash
git stash push -m "stash message"       # stash当前工作区
git stash apply [index]                 # 弹出stash应用到工作区
git stash list                          # 列出当前stash列表
git stash clear                         # 清空stash列表
git stash drop [index]                  # 删除某个stash

## 分支管理/合并
git merge develop                       # 合并develop分支到当前分支


## 其他
git commit --amend                      # 修改本次commit信息


## 紧急修复
git reflog                              # 查看git操作历史
