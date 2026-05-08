详细课程内容
---

### 模块一：寻找 & 获取项目

#### 第一节：认识 GitHub

先建立直觉，不讲技术细节。可以用这个类比切入：

> GitHub 就像一个**公开的代码图书馆**，全世界的开发者把自己的项目放在上面，你可以去参考、复用，也可以把自己的项目放进去。

顺带解释清楚两个容易混的概念：

- **Git**：一个工具，帮你记录文件的每一次修改历史（就像文档的「版本记录」，但更强大）
- **GitHub**：一个网站，帮你把 Git 管理的项目存到云上，并且可以跟别人共享

#### 第二节：搜索好项目

在 GitHub 上找项目的几个实用技巧，可以边演示边讲：

- **Stars 数量**：类似「收藏数」，越高说明越受认可
- **Topics 标签**：每个项目可以打标签，按标签浏览效率更高
- **搜索语法**：`awesome python`、`stars:>1000 language:javascript` 这类组合搜索
- **Trending 页面**：`github.com/trending`，看近期最热门的项目

#### 第三节：读懂项目主页

把项目主页的结构一一讲清楚：

| 区域          | 是什么       | 怎么用               |
| ------------- | ------------ | -------------------- |
| README        | 项目说明书   | 先读这里，看能不能用 |
| Stars / Forks | 受欢迎程度   | 判断项目是否活跃     |
| Issues        | 问题反馈区   | 看别人踩过的坑       |
| License       | 使用授权     | MIT 最宽松，可商用   |
| Last commit   | 最近更新时间 | 判断项目是否还在维护 |

#### 第四节：把项目下载到本地

两种方式，帮他理解各自的适用场景：

**Download ZIP**：点击绿色按钮直接下载，简单，但下载后和 GitHub 断开联系，后续更新要重新下载。

**git clone**：用终端命令下载，下载后本地版本和 GitHub 保持「关联」，可以用 `git pull` 随时同步最新内容。

```bash
# 打开 macOS 终端，运行：
git clone https://github.com/用户名/项目名.git
```

> **建议**：如果只是想看看代码或直接用，ZIP 就够了。如果打算长期跟进或者自己改，用 clone。

------

### 模块二：上传 & 部署项目

#### 第一节：Git 是什么（建立心智模型）

这里是基础薄弱学员最容易卡住的地方，建议用**游戏存档**类比：

> 打游戏时，你在打大boss之前会先「存档」，打完了存一次，通关了再存一次。Git 做的事差不多——你每改一批代码，就手动「存」一次，每次存档都有备注，以后随时可以回到任意存档点。

核心命令对应关系：

| Git 命令     | 类比                   | 实际作用                 |
| ------------ | ---------------------- | ------------------------ |
| `git add`    | 把要存的东西放进存档袋 | 选择哪些文件纳入这次记录 |
| `git commit` | 按下存档键，写存档备注 | 正式记录这次改动         |
| `git push`   | 把存档上传到云端服务器 | 同步到 GitHub            |

#### 第二节：创建第一个仓库

准备一个极简的示例网页项目（三个文件就够）：

```
my-first-site/
├── index.html
├── style.css
└── script.js
```

`index.html` 内容示例：

```html
<!DOCTYPE html>
<html>
<head>
  <title>我的第一个网站</title>
  <link rel="stylesheet" href="style.css">
</head>
<body>
  <h1>你好，世界！</h1>
  <p>这是我用 GitHub + Netlify 部署的第一个网站。</p>
</body>
</html>
```

然后在 GitHub 网页上点击「New repository」创建仓库，命名规范、public/private 选择一并讲解。

#### 第三节：三步走 add / commit / push

在终端里一步一步执行，每步都解释在做什么：

```bash
# 第一步：进入项目文件夹
cd my-first-site

# 初始化 Git（只做一次）
git init
git remote add origin https://github.com/你的用户名/仓库名.git

# 第二步：add — 选中所有文件
git add .

# 第三步：commit — 写备注，正式存档
git commit -m "第一次上传，添加了主页"

# 第四步：push — 推送到 GitHub
git push -u origin main
```

> **小技巧**：每次改完代码，记得走一遍 `add → commit → push` 这个流程，养成习惯。

#### 第四节：Netlify 一键部署

这部分完全在网页上操作，不需要终端，学员接受度高：

1. 注册 / 登录 [netlify.com](https://netlify.com/)
2. 点击「Add new site」→「Import an existing project」
3. 选择「GitHub」，授权后找到刚才的仓库
4. 点击「Deploy」，等几秒钟
5. 拿到一个 `xxx.netlify.app` 的网址，可以直接分享

**Netlify 最值得强调的一点**：以后每次 `git push` 到 GitHub，Netlify 会**自动重新部署**，网站内容自动更新，不需要任何额外操作。

