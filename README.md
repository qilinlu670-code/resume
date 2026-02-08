# 简历网页（静态版）

这个站点是一个**纯静态**的一页式简历网站：`index.html` + `assets/` 图片资源。

## 1) 本地预览

### 方式 A：直接双击打开
- 直接用浏览器打开 `index.html` 即可预览。

### 方式 B：用本地服务器（更推荐）
在项目根目录执行：

```bash
python3 -m http.server 8000
```

然后访问：`http://localhost:8000/`

> 用本地服务器的好处：避免某些浏览器对本地文件加载资源的限制。

## 2) 如何改成你的信息（最重要）

打开 `index.html`，搜索：`const profileData = {`。

你只需要改 `profileData` 里的内容即可（姓名、岗位、简介、教育、经历、技能、联系方式、图片等）。

- **联系方式**：在 `profileData.contact` 里改邮箱/电话/社交链接。
- **经历**：在 `profileData.experience` 数组里改公司/岗位/项目/结果。
- **技能**：在 `profileData.skills` 和 `profileData.skillCategories` 里改。
- **图片**：
  1. 把你自己的图片放到 `assets/` 目录；
  2. 然后在 `profileData.hobbyImages` 里把路径替换成你的图片路径（例如 `assets/xxx.jpg`）。

> 页面支持中英文切换：`profileData` 里每个字段都有 `xxx` / `xxxEn` 两个版本。

## 3) 部署到线上（不需要后端）

这是静态站点，部署平台任选：

### GitHub Pages
1. 新建仓库，把 `index.html` 和 `assets/`（以及 README.md）放到仓库根目录。
2. GitHub -> Settings -> Pages -> 选择从 `main` 分支部署。
3. 等待生成后，会得到一个 `https://xxx.github.io/xxx/` 的地址。

### Vercel / Netlify / Cloudflare Pages
- 选择导入仓库（或拖拽上传文件夹）。
- **Build Command**：留空
- **Output Directory**：留空 / `.`（根目录）

## 4) 常见小改动

- **浏览器标签页标题**：改 `index.html` 顶部的 `<title>...</title>`
- **头像/首屏信息**：都在 `profileData` 里
- **主题色**：搜索 `apple-blue` 或 `#0071E3` 替换
- **是否需要自定义鼠标（cursor）**：搜索 `cursor: none;` 可以关闭

祝你上线顺利！


## 5) 音乐播放按钮（可选）

页面右下角新增了一个播放/暂停按钮，默认会尝试加载：

- `assets/audio/river-flows-in-you.mp3`

出于版权原因，这个仓库**不自带**音乐文件。你需要把你拥有版权/授权的音频（mp3）放到上述路径，并保持文件名一致。

> 如果你不需要音乐功能，直接在 `index.html` 里搜索 `Music Toggle` 删除按钮代码即可。

