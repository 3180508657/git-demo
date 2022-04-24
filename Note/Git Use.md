# Git

[TOC]

##概述

- 免费开源-分布式版本控制系统

  - 记录文件内容变化的系统

  - 可记录文件、修改历史记录、查看历史版本（适用团队协作）

  - 廉价本地库、暂存区域、多个工作流分支

  - 工作机制（Linus开发）

    | 工作区git add        | 本地磁盘         |
    | -------------------- | ---------------- |
    | **暂存区git commit** | **临时存储**     |
    | **本地库push**       | **历史版本**     |
    | **远程库**           | **代码托管中心** |

  - 代码托管中心

    - 局域网GitLab
    - 互联网GitHub（外网）Gitee码云

- [下载git](https://git-scm.com)

- 集中式版本控制工具CVS、SVN、VSS...

  - 单一服务器=>中央服务器单点故障问题（无法提交更新）

## Git常用命令

| **命令名称**                                    | **作用**                                    |
| :---------------------------------------------- | :------------------------------------------ |
| git config --global user.name 用户名            | 设置用户签名（区分操作者、否则无法提交）    |
| git config --global user.email 邮箱             | 设置用户签名（win用户.gitconfig查看）       |
| git init                                        | 初始化本地库（对应文件夹打开Git Bash Here） |
| git status                                      | 查看本地库状态                              |
| git add 文件名 （ .所有文件）、 git rm --cached | 添加移除暂存区域                            |
| git commit -m "日志信息" 文件名                 | 提交本地库                                  |
| git reflog、git log                             | 查看历史记录提交者                          |
| git reset --hard 版本号                         | 版本穿梭                                    |

Git 切换版本原理

| head        |              |           |
| :---------- | :----------- | :-------- |
| **master**  |              |           |
| **first->** | **second->** | **third** |

## Git分支



- 同时并行多个功能开发，提高开发效率

- 某一个分支开发失败，不会对其他分支产生影响

- 常用分支操作命令

  | 常用命令            | 作用                       |
  | :------------------ | :------------------------- |
  | git branch 分支名   | 创建分支                   |
  | git branch -v       | 查看分支                   |
  | git checkout 分支名 | 切换分支                   |
  | git merge 分支名    | 把指定分支合并到当前分支上 |

- 合并冲突（两个分支在同一个文件的同一个位置有完全不同的修改）=>手动合并代码（删除不需要代码和提醒注释）=>提交本地库时无文件名

分支原理 head指针同上

## Github操作

[Github网址](https://github.com)

- New repository创建远程库（名称应与本地库同名git-demo）

- 常用远程库操作命令

  | 命令名称                                        | 作用                                                         |
  | :---------------------------------------------- | :----------------------------------------------------------- |
  | git remote -v                                   | 查看当前所有远程地址别名                                     |
  | git remote add 别名 远程地址 git remote rm 别名 | 起别名 删除远程库                                            |
  | git push 别名 分支                              | 推送本地分支的内容到远程仓库                                 |
  | git clone 远程地址                              | 将远程库内容克隆到本地                                       |
  | git pull 远程别名 远程分支名                    | 将远程库对于分支拉下来与当前本地分支直接合并（拉取代码、初始化本地库、创建别名） |

- 团队内协作->合作->管理访问权限 ->发送邀请函地址（本机修改凭借管理器）

- 跨团队协作->账号/git-demo->Fork->修改->Pull requests->Merge pull request

- SSH免密登录 ssh-keygen -t rsa -C 账号邮箱 -> 拷贝公钥 -> Settings  ->添加公钥

## IDEA集成Git

- 配置Git忽略文件->家目录下创建git.ignore文件

- [git.ignore常用模板](https://blog.csdn.net/elesos/article/details/79236037)

- ```
  [core]
  	excludesfile = git.ignore文件位置(\=>/)
  ```

- IDEA设置版本控制->bin\git.exe路径

- VCS->创建git仓库->添加暂存区->Gitadd(取消忽略)->提交本地库->左下角Git查看历史版本->右下角新建切换分支

## IDEA集成GitHub

- [个人访问令牌登录GitHub](https://github.com/settings/tokens/new) 
- SSH免密登录：push自定义别名ssh-git
- pull拉取保证本地代码版本更新->push
- github克隆（从无到有）

## Gitee操作

- [gitee](https://gitee.com)
- 安装gitee插件

## GitLab

- [gitlab](https://gitlab.com/)（使用MIT许可证的基于网络的Git仓库管理工具）

- 服务器准备CentOs7以上版本、内存4G、磁盘50G、关闭防火墙、配置好主机名gitlab-server和IP、确保服务器能上网

- C:\Windows\System32\drivers\etc（查看配置映射地址）

- [安装包下载](https://packages.gitlab.com/gitlab/gitlab-ce/packages/el/7/gitlab-ce-14.10.0-ce.0.el7.x86_64.rpm) 准备安装包上传服务器/opt/module

- [安装脚本](https://blog.csdn.net/Coder_Hello_World/article/details/81709065?spm=1001.2101.3001.6650.14&utm_medium=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-14.pc_relevant_paycolumn_v3&depth_1-utm_source=distribute.pc_relevant.none-task-blog-2%7Edefault%7EBlogCommendFromBaidu%7ERate-14.pc_relevant_paycolumn_v3&utm_relevant_index=18)->使用主机名或IP地址访问Gitlab服务

- IDEA集成gitlab

  
