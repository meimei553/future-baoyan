# Git 术语清单（详细实用版）

## 一、仓库与对象

- **Repository / repo**：版本库，存放完整历史与工作文件。
- **Working tree / working directory**：工作区，你正在编辑的文件。
- **Staging area / index**：暂存区，准备下次提交的内容（git add 进去）。
- **.git**：仓库元数据目录（对象、引用、配置），一般别手改。
- **Bare repository**：裸仓库，没有工作区，常作服务器端中心库。
- **Object**：Git 内部对象（blob / tree / commit / tag）。
- **Blob**：文件内容快照（不管文件名）。
- **Tree**：目录树，指向 blob 和子 tree。
- **Commit**：提交对象：指向一个 tree，并记录父提交、作者、时间、说明。
- **Tag object**：带说明的附注标签对象（区别于轻量标签）。
- **SHA-1 / hash / commit id**：对象的唯一指纹（常写前 7 位短 hash）。
- **Ref**：引用，给某个 commit 起的名字（分支、标签、HEAD 等）。
- **HEAD**：当前所在位置指针；一般指向某分支，脱离分支时为 detached HEAD。
- **Detached HEAD**：HEAD 直接指某个 commit，不在分支上；再提交容易“丢”。
- **Orphan branch**：没有父提交的新根分支。

## 二、日常命令对应概念

- **init**：在当前目录初始化新仓库。
- **clone**：克隆远程仓库到本地（含历史）。
- **status**：看工作区/暂存区相对 HEAD 的状态。
- **add**：把改动放进暂存区。
- **commit**：把暂存区做成一次新提交。
- **log**：看提交历史。
- **diff**：看差异（工作区 vs 暂存区，或提交之间）。
- **show**：看某次提交的详情与补丁。
- **checkout / switch**：切换分支或恢复文件（新版推荐 switch 切分支、restore 恢复文件）。
- **restore**：恢复工作区或暂存区文件内容。
- **reset**：移动 HEAD/分支，并可改暂存区、工作区（见 soft/mixed/hard）。
- **rm / mv**：从 Git 跟踪中删除或重命名（可配合工作区）。
- **clean**：清掉未跟踪文件（慎用）。
- **stash**：把未提交改动暂存到一旁，工作区变干净。
- **stash pop / apply**：取回 stash（pop 会删掉那条 stash）。
- **ignore / .gitignore**：忽略哪些文件不纳入版本控制。
- **force add（-f）**：强制添加本该被 ignore 的文件。

## 三、分支与合并

- **Branch**：可移动的提交指针，指向一条开发线最新 commit。
- **Local branch**：本地分支。
- **Remote-tracking branch**：远程跟踪分支（如 origin/main），只读镜像远程状态。
- **Upstream**：当前分支跟踪的远程分支（push/pull 默认目标）。
- **Merge**：把另一分支的历史合进来，可能产生 merge commit。
- **Merge commit**：有两个（或多个）父提交的合并提交。
- **Fast-forward**：目标分支没有分叉，指针直接前移，无合并提交。
- **Three-way merge**：用共同祖先 + 两边 tip 做三方合并。
- **Conflict**：两边改同一处，自动合并不了，需手动解决。
- **Resolve**：解决冲突后 add 再 commit（或继续 rebase/cherry-pick）。
- **Rebase**：把一串提交“挪”到另一基线上重放，历史更直。
- **Interactive rebase（-i）**：交互变基：改序、压缩、改说明、删提交。
- **Squash**：多个提交压成一个。
- **Fixup**：类似 squash，提交说明通常丢弃。
- **Cherry-pick**：只挑选某几个提交应用到当前分支。
- **Revert**：用一次新提交“反做”某次旧提交（安全，适合已推送历史）。
- **Bisect**：二分查找引入 bug 的那次提交。
- **Reflog**：引用日志，记录 HEAD/分支动过哪些位置，用来救“丢”的提交。

## 四、reset 三种模式（实用）

- **--soft**：只动分支指针，暂存区与工作区不动。
- **--mixed（默认）**：动指针 + 清空暂存区，工作区文件保留。
- **--hard**：指针、暂存区、工作区一起回到目标提交（未提交改动会丢）。

## 五、远程协作

- **Remote**：远程仓库别名（常见 origin）。
- **origin**：默认远程名。
- **fetch**：下载远程新提交与引用，不自动合并到当前分支。
- **pull**：fetch + merge（或配置成 rebase）。
- **push**：把本地提交推到远程。
- **push -u / --set-upstream**：推送并设置上游跟踪。
- **force push（--force / --force-with-lease）**：强推改写远程历史；lease 更安全，远程有别人新提交会拒绝。
- **Pull request / Merge request**：在托管平台上请求合并（Git 本身无此对象，是 GitHub/GitLab 概念）。
- **Tracking**：本地分支与远程分支的对应关系。
- **Ahead / behind**：本地比上游超前/落后几个提交。

## 六、历史与查看

- **Ancestor / descendant**：祖先 / 后代提交。
- **Parent**：父提交；合并提交有多个 parent。
- **Root commit**：没有父提交的最初提交。
- **DAG**：提交形成的有向无环图。
- **Blame / annotate**：按行显示最后修改者与提交。
- **Pickaxe**：在历史里搜增删某段文本的提交。
- **Pathspec**：限定路径的匹配表达式。
- **Glob**：通配模式（*.o 等）。
- **Porcelain / plumbing**：面向人的高层命令 / 面向脚本的底层命令。

## 七、标签与版本

- **Lightweight tag**：轻量标签，只是一个指向 commit 的名字。
- **Annotated tag**：附注标签，含作者、时间、说明，可签名。
- **Semantic versioning（semver）**：如 1.2.3，常与 tag/release 一起用。

## 八、配置与身份

- **git config**：配置（user / local / system）。
- **user.name / user.email**：提交作者信息。
- **Author vs Committer**：作者 / 提交者（可不同，rebase 后常见）。
- **core.editor**：写提交说明用的编辑器。
- **credential helper**：帮你存远程账号凭证。
- **SSH vs HTTPS**：两种远程访问方式。
- **GPG / SSH signing**：给 commit/tag 做签名验证。

## 九、暂存与部分提交

- **Hunk**：diff 里的一块连续改动。
- **git add -p**：按 hunk 挑选暂存。
- **git commit -p**：交互挑选后提交。
- **Amend**：改写最近一次提交（补文件或改说明）；已推送慎用。

## 十、子模块与大文件

- **Submodule**：在仓库里嵌套引用另一个 Git 仓库（固定到某 commit）。
- **Subtree**：另一种把外部项目树并入的方式。
- **LFS（Git Large File Storage）**：大文件指针化，真实内容放 LFS 服务器。
- **Sparse checkout**：只检出仓库的一部分路径。
- **Partial clone / shallow clone**：浅克隆（--depth）或部分克隆，少下历史/大对象。
- **Shallow**：历史深度有限的克隆。

## 十一、钩子与自动化

- **Hook**：仓库脚本钩子（pre-commit、pre-push、commit-msg 等）。
- **pre-commit**：提交前检查（格式、测试等）。
- **CI 触发**：常由 push/PR 钩到外部 CI（非 Git 内建，但工作流相关）。

## 十二、工作流常用词

- **Feature branch**：功能分支。
- **Mainline / trunk**：主线（常即 main/master）。
- **Hotfix**：线上紧急修复分支。
- **Release branch**：发布分支。
- **Topic branch**：围绕一个主题的短分支。
- **Forking workflow / GitHub flow / Git Flow**：常见协作流程名。
- **Code review**：代码评审（平台侧配合 PR）。
- **Protected branch**：平台保护分支，限制直推、要求评审/CI。

## 十三、状态与文件分类

- **Tracked**：已被 Git 跟踪的文件。
- **Untracked**：从未 add，或不在跟踪中的文件。
- **Modified**：已跟踪且工作区有改动。
- **Staged**：已进入暂存区。
- **Deleted / renamed**：删除 / 重命名（Git 常靠相似度推断 rename）。
- **Unmerged**：冲突未解决状态。

## 十四、危险与救援（实用）

- **丢失提交**：先 reflog 找 hash，再 branch/checkout/cherry-pick 救回。
- **误 hard reset**：立刻 reflog，一般还能找回。
- **误删分支**：reflog 或原 tip 的 hash 重建分支。
- **Never rewrite shared history**：已共享的历史不要随意 rebase/force push。
- **--force-with-lease**：强推前确认远程没别人新推送。
- **Recover with fsck**：极端情况用 git fsck 找 dangling commit。

## 十五、常见命令速查（术语落地）

```text
git clone <url>
git status
git add <file> | git add -p
git commit -m "msg" | git commit --amend
git log --oneline --graph --decorate
git diff / git diff --staged
git branch / git switch <name> / git switch -c <new>
git merge <branch>
git rebase <branch> | git rebase -i HEAD~n
git cherry-pick <sha>
git revert <sha>
git stash / git stash pop
git fetch / git pull / git push -u origin <branch>
git tag -a v1.0 -m "msg"
git remote -v
git reflog
git bisect start
```

## 十六、和 GitHub 易混但要分清的

- **Git**：分布式版本控制系统本身。
- **GitHub**：基于 Git 的托管与协作平台（还有 PR、Issue、Actions 等）。
- **PR / Issue / Actions**：平台概念，不是 Git 核心对象（但日常和 Git 一起用）。

使用建议：本地实验用 throwaway 分支；改已推送历史优先 revert；不确定时先 status + log --graph，再动手 reset/rebase。
