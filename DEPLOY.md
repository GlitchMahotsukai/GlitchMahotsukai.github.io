# 🚀 博客部署清单

## ✅ 已完成

- [x] Hugo 环境准备
- [x] 创建博客项目结构
- [x] 配置多语言支持（中文/英文）
- [x] 设计极简主题（模仿 okmij.org/ftp/ 风格）
- [x] 配置 Decap CMS 可视化编辑器
- [x] 创建示例文章和页面
- [x] 配置 GitHub Actions 自动部署
- [x] 支持多媒体嵌入（图片、视频、音频）

## 📋 你需要完成的步骤

### 1️⃣ 创建 GitHub 账号（如果还没有）
访问 https://github.com 注册

### 2️⃣ 创建 GitHub 仓库
- 仓库名：`你的用户名.github.io`
- 设为公开仓库
- 不要初始化（不要添加 README）

### 3️⃣ 推送代码到 GitHub

打开终端，执行以下命令（替换为你的信息）：

```bash
cd /home/admin/openclaw/workspace/my-blog

# 配置 Git（首次使用需要）
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"

# 添加远程仓库
git remote add origin https://github.com/你的用户名/你的用户名.github.io.git

# 推送代码
git branch -M master
git add .
git commit -m "Initial commit"
git push -u origin master
```

### 4️⃣ 启用 GitHub Pages
1. 进入仓库 → Settings → Pages
2. Source 选择 **GitHub Actions**
3. 等待自动部署（约 1-2 分钟）
4. 访问 `https://你的用户名.github.io` 查看网站

### 5️⃣ 启用可视化编辑器
1. 访问 `https://你的用户名.github.io/admin/`
2. 使用 GitHub 账号授权登录
3. 就可以开始写文章了！

### 6️⃣ 注册 dnshe.com 域名
1. 访问 https://www.dnshe.com/
2. 注册免费域名（推荐：.cc.cd 或 .de5.net）
3. 完成人机验证

### 7️⃣ 配置域名解析
在 dnshe.com 控制台添加：
- 类型：CNAME
- 主机记录：@
- 记录值：你的用户名.github.io

### 8️⃣ 绑定自定义域名
1. 修改 `hugo.toml` 中的 `baseURL` 为你的域名
2. 创建 `static/CNAME` 文件，内容是你的域名
3. 提交到 GitHub

---

## 📝 可视化编辑器使用

访问：`https://你的域名/admin/`

- **博客文章** - 创建/编辑文章
- **页面** - 创建/编辑静态页面
- 上传图片 - 直接在编辑器中拖拽上传
- 插入视频 - 使用 HTML 嵌入代码

---

## 🎬 多媒体嵌入示例

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

有任何问题随时告诉我！😊
