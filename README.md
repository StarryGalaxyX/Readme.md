# Readme.md
1. 生成 SSH 密钥（如果还没有）
首先，你需要确保你的本地计算机上有一个 SSH 密钥，并且将它添加到 GitHub 上。这样可以避免每次推送代码时都输入用户名和密码。

a. 生成 SSH 密钥
在终端中执行以下命令来生成 SSH 密钥：

bash
复制代码
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
提示你输入文件保存位置时，可以直接按回车使用默认路径（~/.ssh/id_rsa）。
提示输入密码时，你可以选择设置密码保护，或者直接按回车跳过。
b. 查看并复制公钥
生成完 SSH 密钥后，公钥会保存在 ~/.ssh/id_rsa.pub 文件中。你可以用以下命令查看并复制公钥内容：

bash
复制代码
cat ~/.ssh/id_rsa.pub
复制输出的所有内容。

c. 将公钥添加到 GitHub
登录 GitHub 账户。
在右上角点击你的头像，选择 Settings。
在左侧导航中选择 SSH and GPG keys。
点击 New SSH key，在 Title 字段填入一个描述（如 "My Laptop SSH Key"），然后在 Key 字段粘贴你复制的公钥。
点击 Add SSH key。
2. 克隆远程仓库
如果你还没有将 GitHub 仓库克隆到本地，可以通过 SSH 克隆仓库。使用以下命令：

bash
复制代码
git clone git@github.com:your_username/your_repository.git
这里的 your_username 是你的 GitHub 用户名，your_repository 是你仓库的名称。

3. 进行代码修改
进入仓库文件夹，并修改你需要修改的文件：

bash
复制代码
cd your_repository
你可以使用任何编辑器修改代码，如 vim、nano 或者直接在文件管理器中编辑。

4. 查看代码修改状态
修改文件后，使用以下命令查看修改的文件：

bash
复制代码
git status
Git 会列出所有已修改但未提交的文件。你可以看到修改的文件都标记为 modified。

5. 将修改的文件添加到暂存区
将修改的文件添加到暂存区（staging area），准备提交：

bash
复制代码
git add <file_name>
如果你想一次性添加所有修改的文件，可以使用：

bash
复制代码
git add .
6. 提交代码
提交文件到本地仓库时，需要添加提交信息来描述这次更改：

bash
复制代码
git commit -m "Your commit message here"
确保提交信息简洁明了，能够清晰地描述这次修改的内容。

7. 查看提交日志（可选）
提交完成后，你可以查看提交历史，确认自己的提交是否成功：

bash
复制代码
git log
你会看到类似于以下的输出：

sql
复制代码
commit abc1234567890abcdef
Author: Your Name <your_email@example.com>
Date:   Wed Oct 25 16:53:19 2024 +0800

    Your commit message here
8. 推送代码到远程仓库
将本地的提交推送到 GitHub 仓库：

bash
复制代码
git push origin main
origin 是远程仓库的默认名称。
main 是你要推送的分支名。如果你使用的是旧版本的 Git，默认分支可能是 master，请根据实际情况替换。
如果你是第一次使用 SSH 推送代码，Git 会在后台验证你的 SSH 密钥。如果一切正常，你将不需要输入用户名和密码。

9. 验证推送结果
推送完成后，你可以通过访问 GitHub 上的仓库页面，检查是否成功提交了代码。

你也可以使用以下命令来查看远程仓库的状态：

bash
复制代码
git remote -v
这会显示你当前设置的远程仓库 URL。确保它是以 git@github.com 开头，表示使用 SSH 连接。

总结：
生成并配置 SSH 密钥，将公钥添加到 GitHub。
使用 SSH 克隆仓库。
修改代码，并通过 git add 将更改添加到暂存区。
使用 git commit 提交更改，并添加有意义的提交信息。
使用 git push 将本地代码推送到 GitHub。
通过 SSH 推送代码的过程会避免每次都输入用户名和密码，只要 SSH 密钥正确配置，Git 就会自动完成身份验证。

