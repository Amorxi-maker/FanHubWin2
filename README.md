# WINWIN Fan Hub —— 董思成粉丝资源中心 🦊

欢迎来到 **WINWIN Fan Hub**！这是一个专为艺人**董思成（WinWin）**打造的非盈利高品质单页面（SPA）粉丝资源中心网页。本站完整记录并收录了董思成的影视剧作品、综艺节目、舞台直拍、深度采访以及全球粉丝的精美二次创作内容。

---

## 🌟 网站核心板块

本网站采用现代前端扁平化交互设计，所有内容通过底部核心数据对象进行动态渲染，包含以下两大核心分类：

### 🎬 Categories（作品馆）
*   **TV Series / 影视剧作品**：完整收录《五福临门》（杨羡）、《良陈美锦》（叶限）、《冰雪谣》（司徒威涟）、《25小时恋爱》（言樾）等领衔主演及参演的优秀剧集。
*   **Variety Shows / 综艺节目**：追踪从常驻综艺《五十公里桃花坞5》、《我们的师父》到经典慢综艺、热门真人秀的精彩瞬间。
*   **Stage Focus / 舞台直拍**：汇集 WayV（威神V）及 NCT 期间的惊艳舞台、中国舞/现代舞专属直拍及练习室版本。
*   **Interview / 采访对话**：深度记录各大时尚杂志（COSMO、GQ、ELLE等）大片幕后、专访与趣味快问快答。
*   **Fan-made / 粉丝创作**：留存海内外粉丝制作的高燃神仙剪辑、手绘插画及应援项目纪实。

### 📸 Gallery（视觉画廊）
*   **Period Costume / 古装造型**：记录由画中走出的古装美男子杨羡、叶限等经典角色剧照。
*   **Casual Wear / 日常私服**：捕捉机场私服、生活随拍与自在穿搭的穿衣美学。
*   **Red Carpet & Events / 盛典红毯**：聚焦各大时尚之夜、颁奖典礼等聚光灯下的高光西装与高定造型。
*   **HD Wallpapers / 高清壁纸**：为同好粉丝倾心准备的无水印桌面及手机超清壁纸合集。

---

## ⚙️ 开发者维护指南（如何更新图片与视频链接）

为了保证网页的流畅与极简性，本系统采用 **数据驱动渲染** 模式。无需修改繁琐的 HTML 标签，所有的内容、视频跳转链接及封面图片全部存放在 `index.html` 最底部的 `<script>` 标签内。

### 1. 更新影视剧/综艺/舞台内容
找到代码底部的 `const CONTENT = { ... }`，定位到对应的分类数组（如 `'tv-series'`）：
```javascript
items: [
  { 
    title: '五福临门', 
    cover: 'images/wfwlm.jpg',                 // 👈 替换为您存放在 images 文件夹下的本地图片相对路径
    url: 'https://www.mgtv.com/h/617394.html', // 👈 替换为芒果TV/腾讯视频等官方实际播放或直达链接
    intro: '角色：杨羡（领衔主演）| 2025 古装轻喜剧' 
  }
]
```

### 2. 更新 Gallery 画廊美图
定位到相册分类（如 `'sifu'`）：
```javascript
images: [
  { src: 'images/sifu1.jpg', label: '日常机场私服' }, // 👈 src 替换为高清图路径，label 替换为图片描述文案
  { src: 'images/sifu2.jpg', label: '日常穿搭随拍' }
]
```

> 📌 **多媒体文件存放规范**：
> 强烈建议在项目根目录下新建一个 `images/` 文件夹。将所有封面图、高清美图统一命名后放入该文件夹中，并在代码中使用 `images/文件名.jpg` 的相对路径进行引用。这样可以确保图片随代码一起托管至 GitHub，永久有效且不惧网络防盗链。

---

## 🚀 部署与上线说明 (GitHub Pages)

本网页是一套纯前端的 SPA 系统，完美兼容并支持通过 **GitHub Pages** 进行免费的静态网页托管：

1. **环境整理**：请确保主入口文件 `index.html` 位于项目的根目录。样式表 `main.css` 请根据您在 HTML 里的引用路径进行正确摆放（如果引用的路径是 `/styles/main.css`，请在根目录下建立 `styles` 文件夹并放入其中）。
2. **开启托管**：
    * 进入您在 GitHub 上的仓库页面 `FanHubWinWin`。
    * 点击顶部导航栏的 **Settings**（设置）选项卡。
    * 选择左侧边栏的 **Pages** 选项。
    * 将 **Build and deployment** 下的 **Branch**（分支）由 `None` 切换为 **`main`**，目录保持默认的 `/ (root)`。
    * 点击 **Save**（保存）。
3. **正式上线**：等待 1-2 分钟后刷新页面，顶部会出现一个绿色的专属网址。将该网址分享给全球的同好吧！

---

## 📜 声明 / Disclaimer

* **非盈利性质**：本站仅为粉丝自制非盈利个人网站，不含有任何商业盈利行为。本站所有资源均来自网络收集，仅供同好交流分享。
* **官方关联澄清**：本站与董思成（WinWin）所属经纪公司（SM Entertainment）及国内官方工作室无任何官方或商业关联。
* **This is a non-profit website fan-made exclusively for WinWin (Dong Sicheng). It is strictly for entertainment, archival, and fan-sharing purposes. This website is not affiliated with, endorsed by, managed by, or in any way officially connected to SM Entertainment or his official sub-labels/management studios.**
