# Git命令

## 本地仓库修改后如何同步到GitHub

```
cd /path/to/your/repo         # 进入你的本地仓库
git status                    # 查看修改的文件
git add .                     # 添加所有修改的文件到暂存区
git commit -m "Updated files" # 提交更改
git pull origin main          # 拉取远程仓库的最新更改
git push origin main          # 将本地更改推送到远程仓库

git checkout main #确保你在本地仓库的主分支上
git pull origin main
```

## 如何将GitHub仓库同步到本地仓库

```
#如果完全没有本地仓库则直接
git clone GitHub_repo

#如果要更新GitHub到本地则
git checkout main   #确保你在本地仓库的主分支上
git pull origin main  #从远程仓库拉取最新的更改
```

## 本地git和GitHub连接问题

```
HTTPS方式又称为邮箱方式：
git config --global user.name
git config --global user.email
如果这些命令返回了你的 GitHub 账号的用户名和邮箱（与你 GitHub 账号中的信息匹配），说明你在本地已经配置了 Git 用户信息。

这个是使用SSH连接到GitHub
ssh -T git@github.com
成功则为：Hi LaplaceMonster! You've successfully authenticated, but GitHub does not provide shell access.
如果出现错误，说明你的 SSH 密钥可能没有正确添加到 GitHub，你可以按以下步骤检查：
运行 ls ~/.ssh/，查看是否已有 SSH 密钥（id_rsa 和 id_rsa.pub）。
如果没有，使用 ssh-keygen -t rsa -b 4096 -C "your-email@example.com" 生成一个 SSH 密钥，并将 id_rsa.pub 的内容添加到 GitHub 的 SSH and GPG keys 设置中。


如果你已经克隆了某个 GitHub 仓库，可以用以下命令检查它是否与 GitHub 关联：
git remote -v

如果看到类似：
origin  git@github.com:your-username/repo-name.git (fetch)
origin  git@github.com:your-username/repo-name.git (push)
或者：
origin  https://github.com/your-username/repo-name.git (fetch)
origin  https://github.com/your-username/repo-name.git (push)
说明你已经正确关联到了 GitHub。
```

