# 查看文件命令
1. 不显示隐藏文件：ll|less
2. 显示隐藏文件：  ls -la|less
# 团队协作
1. 创建者 ：push 上传 pull下载
2. 团队成员：clone 下载 push(加入团队)上传
# 跨团队协作
1. fork远程库(给自己复制一份远程库)
2. clone下载
3. push 上传
4. pull request 发起拉取请求
5. 原创建者审核
6. merge拉取合并到原创建者的库
7. 原创建者pull下载到本地
# 设置签名
用户名，邮件地址 
作用：区分不同的开发人
1. 命令
项目，仓库级别：仅在当前库范围内有效
  git config user.name lyq
  git config user.email lyq@163.com 
系统用户级别：登录当前操作系统到的用户范围
  git config --global user.name lyq
  git config --global user.email lyq@163.com 
* 优先级级别
  项目级别优先于系统级别，二者都有时采用项目级别的签名
  二者都没有不允去
2. 信息保存的位置
  仓库级别：当前目录下.git/config
  系统用户级别：~/.gitconfig  
# git 提交本地仓库命令
 wq  退出
 cat 文件名： 查看内容
 git status：状态查询
 git add */文件名：存放到暂存区
 git rm --cached 文件名  ：从暂存区恢复到之前的状态
 git commit 文件名 注释/-m '注释'：从暂存区提交到本地仓库，并添加注释
  注释：对于以添加过得文件，可以用git add 或直接用git commit -a 提交
# git 版本控制命令
 git status：状态查询
 git log ：查看历史提交，日志
 git log --pretty=oneline 每条记录显示一行
 git log  oneline 缩短成7位哈希值，每条记录显示一行
 git reflog 查看日志，包含指针
 tail -n 3 文件名： 只显示最后三行日志
  注释：HEAD指针 指向当前版本
 git reset --hard 索引值7位 ：回到索引值的版本
 git reset --hard HEAD^：往一个^后退一个版本^^后退两步
 git reset --hard HEAD~3：往后退3个版本
  git reset{
    --soft ：只移动指针（本地库）
    --mixed ： 移动指针（本地库） 和暂存区
    --hard： 本地库，暂存区，工作区
  }
  删除文件找回：
    前提：删除前，文件存在的状态提交到本地库
    操作：git reset --hard【指针位置】
      删除操作以提交到本地库，指针指向历史记录
      删除操作尚未提交到本地库，指针位置使用HEAD
 git diff 文件 ：工作区与暂存区比较文件差异
 git diff HEAD 文件 ：工作区与历史记录比较文件差异
 git diff HEAD^ 文件 ：与历史文件比较文件差异
 git diff     ： 比较当前工作区所有文件
# git 分支
  git branch -v       ：分支查询
  git branch 分支名   ：添加分支
  git checkout 分支名 ：切换分支
    合并分支
      切换到要合并到的分支
      git merge 被合并分支名 
    合并冲突：
      编辑文件，删除特殊字符
      把文件修改到满意程度并退出
      git add 文件名
      git commit -m  '日志信息'
        此时commit 一定不能带文件名
# git 基本原理
  哈希算法不可逆
  算法确定，加密结果确定
  内容修改，结果相差大  
  输入一定，输出一定，对应
# git 保存版本的机制
  1. 集中式
    改一次添加一个独立的文件。文件集就是最后的结果
  2. 文件管理机制
    保存快照流，保存文件快照
  3. 管理文件细节
    git 提交对象 树形 
    提交对象及其父对象形成链条
    新建分支其实是新建一个指针，指向原来的文件
    切换分支是移动指针
# 协同开发
* 同一个团队
  1. 克隆clone
    git clone 地址
      把完整远程库下载到本地
      创建origin远程地址别名
      初始化本地厂库
    pull 拉取一次有下面两个功效
      fetch 【远程地址别名，远程分支名】远程下载到本地
      merge 【远程地址别名/远程分支名】合并
  2. 邀请成员
      仓库=》setting=》collaborators 填入要邀请人的账号 复制邀请的连接发送给他
  3. 解决冲突
    不是最新版做的修改，不能推送，必须先拉取
    拉取下来先解决冲突
* 不同团队
  1. fork 
    登录站好进入需要克隆的账号仓库，点击fork，会克隆到自己的仓库
  2. clone到本地
    进行操作，推送到远程库
  3. pull Request
    new pull Request
    create pull Request
    发消息给仓库创建者
  4. 仓库创建者点pull Request 
    点击内容，查看发过来的消息
    可以对话
  5. 审核代码
    commits和files changed查看提交代码和说明
  6. 合并merge pull request
    填写 合并说明 确认合并
  7. 把远程库拉取到本地pull
# ssh 方式
  ssh-keygen -t rsa -C 邮箱名 //生成到用户文件夹下
  cd .ssh/
  ll
  cat id_rsa.pub
  复制内容
  复制到github stting=> ssh and gpg keys=>key
# eclipse 中git用法
  1. 将工程初始化为本地库
    工程=》右键=》Team=》share project =》git=》use or create……=》选中工程=>create repository=》finsh
  2. 设置别名
    add entry=》user.name  user.email
  3. 图标意义
    label decoration 
      金色圆柱加> 表示有被提交的修改
      金色圆柱加  表示没有被提交的修改
      ？             新建文件，还没有对他追踪
      什么图标都没有  忽略的文件
      *             添加到暂存区
      +             新建文件从没有追踪到对他进行追踪
  4. eclipse 中忽略文件
    概念：为管理创建工程而维护的文件
      .classpath文件
      .project 文件
      .settings目录下所有文件
    为什么忽略
      同一个团队，用的版本不同，会冲突
# git 工作流
  master
  hotfix热修复分支 master出现bug在此分支修复，合并到master和develop
  release预发布分支 develop提交的出现bug在此分支修复，合并到master和develop
  develop 开发分支
  小功能分支 开发完成合并到develop
# gitlab服务器搭建 内外网使用