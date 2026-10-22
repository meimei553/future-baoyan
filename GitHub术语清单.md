# GitHub 术语清单（合并完整版）

## 一、基础六词

- **PR（Pull Request）**：提合并请求——把你分支上的改动申请合进目标分支，别人可以看 diff、评论、批准后再合。
- **main**：默认主分支，一般放稳定、可发布的代码。
- **branch（分支）**：从某次提交拉出来的平行线，用来改功能或修 bug，互不影响。
- **issue**：问题/任务单，记 bug、需求、讨论，可关联 PR。
- **CI（Continuous Integration）**：提交或开 PR 时自动跑构建、测试、检查，通了才好合。
- **review（代码评审）**：别人看你的 PR，提意见或批准（approve）。

## 二、仓库与协作

- **Repository / repo**：仓库，一个项目的代码与历史。
- **Fork**：复制别人的仓库到自己账号，方便改再开 PR。
- **Clone**：把远程仓库下载到本地。
- **Remote / origin**：远程地址；origin 通常指你克隆来的那个。
- **Upstream**：上游仓库，fork 场景里常指原作者的仓库。
- **Organization / org**：组织账号，多人共享权限。
- **Collaborator**：协作者，被加进仓库的人。
- **Star / Watch**：星标收藏；Watch 订阅仓库动态。

## 三、分支与提交

- **Commit**：一次提交（改动快照）。
- **SHA / hash**：提交的唯一 ID。
- **HEAD**：当前所在提交指针。
- **Merge**：把一个分支合进另一个。
- **Rebase**：把提交挪到另一基线上重放，历史更直。
- **Fast-forward**：目标分支没有分叉，直接指针前移。
- **Conflict**：两边改了同一处，需手动解决。
- **Cherry-pick**：只挑某几个提交过来。
- **Tag / Release**：打标签；Release 是带说明/附件的正式版本。
- **Default branch**：默认分支，多半是 main。
- **push / pull**：推送到远程 / 从远程拉下来。

## 四、PR 周边

- **Draft PR**：草稿 PR，还没正式求审。
- **Base / head**：PR 合进的目标分支 / 来源分支。
- **Diff**：改动差异。
- **Approve / Request changes / Comment**：评审结论：通过 / 需改 / 仅评论。
- **Merge commit / Squash / Rebase merge**：三种合入方式（保留合并提交 / 压成一条 / 变基合入）。
- **Reviewer / Assignee**：评审人 / 负责人。
- **Label**：标签，分类用。
- **Milestone**：里程碑，把一批 issue/PR 绑到目标版本。
- **Protected branch**：受保护分支，强制评审、CI 通过才能推。

## 五、Issue 与讨论

- **Bug / Feature / Enhancement**：缺陷 / 新功能 / 改进。
- **Discussion**：讨论区（偏开放讨论，不一定是任务）。
- **Project / Project board**：看板（To Do / In Progress 等）。
- **Wiki**：仓库内文档页。
- **Gist**：零散代码片段托管。

## 六、CI / 自动化

- **GitHub Actions**：GitHub 自带的 CI/CD。
- **Workflow**：一套自动化流程（yaml 定义）。
- **Job / Step**：工作流里的任务 / 步骤。
- **Runner**：跑 CI 的机器（GitHub-hosted 或 self-hosted）。
- **Status check**：状态检查（测试、lint 等），常卡 PR。
- **Artifact**：CI 产出的文件（日志、包）。
- **Secret**：仓库/组织级密钥，给 Actions 用。
- **CD（Continuous Deployment/Delivery）**：持续部署/交付，通过后再自动发布。

## 七、安全与质量

- **CODEOWNERS**：文件负责人，改这些文件自动找人审。
- **Dependabot**：依赖更新机器人。
- **Security advisory / Dependabot alert**：安全通告 / 依赖漏洞提醒。
- **Code scanning / Secret scanning**：代码扫描 / 密钥泄露扫描。

## 八、权限与访问

- **SSH key / PAT（Personal Access Token）**：SSH 密钥 / 个人访问令牌，用来推拉代码或调 API。
- **OAuth App / GitHub App**：第三方应用授权方式。
- **Permission**：Read / Write / Admin：读 / 写 / 管理。
- **Visibility**：Public / Private / Internal：公开 / 私有 / 组织内部。

## 九、其它常碰到的

- **Blame**：按行看最后是谁改的。
- **History / Log**：提交历史。
- **Stash（本地 git）**：暂存未提交改动（Git 概念，网页上少见）。
- **LFS（Git Large File Storage）**：大文件单独存。
- **Pages**：用仓库静态文件做站点。
- **Packages**：包仓库（容器镜像、npm 等）。
- **Template repository**：模板仓库，一键生成新项目。
- **Badge**：README 上的状态徽章（构建通过、覆盖率等）。

日常最常碰上：repo、branch、commit、push/pull、PR、review、merge、issue、CI、Actions、main、fork、clone、conflict、release。
