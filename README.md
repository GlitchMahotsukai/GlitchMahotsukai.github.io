# 我的博客 - 部署指南

这是一个使用 Hugo 构建的多语言博客，支持可视化编辑和自动部署。

## 🚀 快速部署步骤

### 第 1 步：创建 GitHub 仓库

1. 登录 GitHub
2. 创建新仓库，命名为 `你的用户名.github.io`
3. 不要初始化仓库（不要添加 README 或 .gitignore）

### 第 2 步：推送代码到 GitHub

```bash
cd /home/admin/openclaw/workspace/my-blog

# 配置 Git（如果还没配置）
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

# 添加远程仓库并推送
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git
git branch -M master
git add .
git commit -m "Initial commit"
git push -u origin master
```

### 第 3 步：启用 GitHub Pages

1. 进入仓库的 **Settings** → **Pages**
2. Source 选择 **GitHub Actions**
3. 等待部署完成（约 1-2 分钟）

### 第 4 步：启用 Decap CMS（可视化编辑器）

1. 进入仓库的 **Settings** → **Pages**
2. 确保 GitHub Pages 已启用
3. 访问 `https://你的用户名.github.io/admin/`
4. 首次访问需要授权 GitHub 账号

### 第 5 步：注册 dnshe.com 域名

1. 访问 https://www.dnshe.com/
2. 注册免费域名（如：yourblog.cc.cd）
3. 完成人机验证

### 第 6 步：配置域名解析

在 dnshe.com 控制台添加 DNS 记录：

| 类型 | 主机记录 | 记录值 |
|------|----------|--------|
| CNAME | @ | 你的用户名.github.io |
| CNAME | www | 你的用户名.github.io |

### 第 7 步：配置自定义域名

1. 修改 `hugo.toml` 中的 `baseURL`：
   ```toml
   baseURL = 'https://你的域名.dnshe.com/'
   ```

2. 在仓库根目录创建 `static/CNAME` 文件：
   ```
   你的域名.dnshe.com
   ```

3. 提交更改：
   ```bash
   git add .
   git commit -m "Add custom domain"
   git push
   ```

---

## ✏️ 使用可视化编辑器

1. 访问 `https://你的域名/admin/`
2. 使用 GitHub 账号登录
3. 点击左侧菜单：
   - **博客文章** - 创建/编辑文章
   - **页面** - 创建/编辑静态页面
4. 编辑完成后点击 **Publish**
5. GitHub Actions 会自动构建并部署

---

## 📸 插入多媒体内容

### 图片
在编辑器中直接上传图片，或使用：
```markdown
![描述](/images/图片文件名.jpg)
```

### YouTube 视频
```html
<iframe width="560" height="315" 
  src="https://www.youtube.com/embed/视频 ID" 
  frameborder="0" allowfullscreen>
</iframe>
```

### B 站视频
```html
<iframe src="//player.bilibili.com/player.html?bvid=视频 BVID" 
  scrolling="no" border="0" frameborder="no" 
  width="100%" height="500">
</iframe>
```

### 音频
```html
<audio controls>
  <source src="/audio/文件名.mp3" type="audio/mpeg">
</audio>
```

---

## 📁 项目结构

```
my-blog/
├── .github/workflows/     # GitHub Actions 部署配置
├── content/               # 博客内容
│   ├── zh/               # 中文内容
│   │   ├── posts/        # 文章
│   │   └── pages/        # 页面
│   └── en/               # 英文内容
├── layouts/              # 网站模板
├── static/               # 静态资源
│   ├── admin/           # Decap CMS 配置
│   └── images/          # 图片文件夹
├── themes/              # Hugo 主题
└── hugo.toml           # Hugo 配置文件
```

---

## 🛠️ 本地预览（可选）

如果需要本地预览：

```bash
cd my-blog
./hugo server -D
```

然后访问 http://localhost:1313

---

## 📞 需要帮助？

有任何问题随时告诉我！
