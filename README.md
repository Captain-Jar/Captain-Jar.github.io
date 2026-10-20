# 我的网站

一个纯静态站点，两个部分：

| 路径 | 是什么 |
|---|---|
| `index.html` | 我的个人主页 |
| `ba/index.html` | 蔚蓝档案 · 养成差量计算器（194 名角色） |
| `assets/` | 主页的样式、头像、图标 |

没有框架、没有构建步骤、没有后端。浏览器直接打开 `index.html` 就能看，
传到 GitHub Pages 就是一个真网站。**成本 0 元。**

---

## 一、3 分钟上线（网页操作，推荐第一次用）

### 1. 建仓库

打开 https://github.com/new

- **Repository name** 填：`agent17cpu.github.io`
  （⚠️ 必须一模一样，`agent17cpu` 是你的 GitHub 用户名。仓库叫这个名字，
  网址才会是 `https://agent17cpu.github.io/` 这一层根目录，而不是 `/仓库名/`）
- 选 **Public**
- 下面三个勾（README / .gitignore / license）**都不要勾**
- 点 `Create repository`

### 2. 上传文件

在新仓库页面点 **`uploading an existing file`**，然后把下面这三样拖进去：

```
index.html
assets            ← 整个文件夹
ba                ← 整个文件夹
```

⚠️ **要把这三个拖进去，不要把 `mysite` 文件夹本身拖进去**，
否则网址会变成 `.../mysite/` 多一层。

拖完点绿色的 `Commit changes`。

### 3. 打开 Pages

仓库页 → **Settings**（右上角）→ 左侧 **Pages**

- **Source**：`Deploy from a branch`
- **Branch**：`main` + `/ (root)` → `Save`

等 1～3 分钟，刷新页面，顶部会出现：

> Your site is live at **https://agent17cpu.github.io/**

手机浏览器也打开一次，确认能看。

---

## 二、命令行版（练 git 用，和上面二选一）

仓库建好之后（第 1 步照做，第 2 步不用），在 `mysite` 文件夹里开 PowerShell：

```powershell
cd 你存放 mysite 的目录
git init
git add .
git commit -m "我的主页 + 蔚蓝档案计算器"
git branch -M main
git remote add origin https://github.com/agent17cpu/agent17cpu.github.io.git
git push -u origin main
```

推送时会弹窗要 GitHub 账号，输完就推上去了（你之前推 `python--practice` 已经配好过，
大概率不会再问）。推完回到第 3 步开 Pages。

> GitHub 连不上时：先把你桌面上的 **FastGithub** 打开，再推。

---

## 三、上线后检查这四条

- [ ] `https://agent17cpu.github.io/` 能打开，头像、按钮都正常
- [ ] 点「打开看看 →」能进计算器，角色头像是图片而不是空白
- [ ] 手机上打开，字不溢出、按钮能点
- [ ] 右上角 🌙 点一下能变深色，刷新后还是深色

---

## 四、以后想改，改哪里

| 想改 | 改哪个文件 | 找什么 |
|---|---|---|
| 名字 | `index.html` | `<h1>Agent17</h1>` 那一行 |
| 一句话介绍 | `index.html` | `<p class="lead">` |
| 邮箱 | `index.html` | 搜索 `mailto:`，**两处都要改** |
| GitHub 链接 | `index.html` | 搜索 `github.com/agent17cpu` |
| 「现在在做什么」 | `index.html` | `<aside class="now">` |
| 项目卡片 | `index.html` | 搜 `<!-- 01 -->` `<!-- 02 -->` `<!-- 03 -->` |
| 配色 | `assets/site.css` | 最上面 `:root` 里的 `--accent` 等变量 |
| 头像 | `assets/avatar.jpg` | 直接替换这张图（正方形最好） |

改完上传：仓库页面 → 点文件 → 右上角铅笔图标 → 改 → `Commit changes`，
1 分钟后网站自动更新。**不用重新上传整个文件夹。**

---

## 五、如果 `github.io` 打不开（备用方案）

GitHub Pages 在国内偶尔会慢或者打不开。换 **Cloudflare Pages**，同样免费：

1. https://dash.cloudflare.com → 注册（邮箱就行，不要钱）
2. 左侧 `Workers & Pages` → `Create` → `Pages` → `Upload assets`
3. 把这个 `mysite` 文件夹整个拖进去 → `Deploy site`
4. 得到一个 `xxx.pages.dev` 的网址

两个地址可以同时存在，哪个快用哪个。

---

## 六、成本

| 项目 | 价格 |
|---|---|
| 域名（`github.io` 二级域名） | 0 元 |
| 托管（GitHub Pages） | 0 元 |
| HTTPS 证书 | 0 元，自动配 |
| 图片 CDN（jsDelivr，计算器用） | 0 元 |

以后想买自己的域名（比如 `agent17.com`），一年几十块，**现在不需要**。
