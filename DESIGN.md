# DESIGN.md — WinWin Fan Hub

## 气质与意象

深青蓝底色上的高奢舞台质感——静谧深青蓝#1A3A4B如深海水幕，页头页脚以清透天蓝#98E5F7如舞台灯光勾勒轮廓，卡片以暗黑毛玻璃层叠浮于深渊之间，大圆角与蓝色微光边缘营造舞台聚光感。导航栏白色字体于天蓝底上清晰可读。Hero区域以真实照片为背景（暗化处理+深色渐变遮罩），叠加轻透渐变遮罩，桌面端文字在左、视频小人居右；移动端垂直堆叠。视频小人弹出动画（pop-in），播完后优雅消失。

关键词：Deep Teal Luxury / Sky Blue Header / Stage Sapphire / Glassmorphism / Blue Ambient Glow / Dark Content

## 配色方案

| 角色 | 色值 | 意象来源 |
|------|------|----------|
| 主背景 | `#1A3A4B` | 深海水幕，静谧深青蓝 |
| 页头页脚 | `#98E5F7` | 清透天蓝，舞台灯光勾勒 |
| 导航栏字体 | `#FFFFFF` | 纯白，天蓝底上清晰可读 |
| 卡片背景（毛玻璃） | `rgba(17,17,21,0.60)` | 暗黑毛玻璃层叠 |
| 卡片实体底色 | `#111115` | 深渊灰黑 |
| 品牌高亮色 | `#2563EB` | 静谧蓝/深邃宝石蓝，核心CTA/高亮/Hover |
| 高亮悬停 | `#1E40AF` | 蓝色加深 |
| 高亮10%透明 | `rgba(37,99,235,0.10)` | 浅蓝背景，标签/badge底色 |
| 蓝色微光霓虹 | `0 0 40px rgba(37,99,235,0.15)` | 卡片hover蓝色光晕 |
| 标签发光蓝字 | `#60A5FA` | 高亮浅蓝，标签/徽章文字 |
| 主文字 | `#F3F4F6` | 雾白，高对比清晰不刺眼 |
| 次文字 | `#9CA3AF` | 柔和丝绸灰 |
| 弱化文字 | `#6B7280` | 标签/注释 |
| 轻量边框 | `rgba(30,41,59,0.50)` | 半透明蓝灰边框 |
| 卡片边框 | `rgba(255,255,255,0.05)` | 极淡白边，毛玻璃质感 |
| Gallery Viewer | `#050506` | 极深黑沉浸对比 |

## 字体排版

- 标题字体：`Playfair Display` + `Noto Serif SC` — 社论衬线体
- 正文字体：`Inter` + `Noto Serif SC` — 无衬线极简可读
- 标题字重：700/900，大字号 48–80px，带微弱蓝色text-shadow
- 正文字体：400/500，字号 13–16px

## 视觉策略

- 纯黑底色 + 静谧蓝霓虹：暗黑高奢舞台聚光
- Hero背景照片暗化处理（brightness 0.55 + 深色渐变遮罩）
- 视频小人弹出动画：pop-in cubic-bezier
- 视频白底处理：mix-blend-mode:screen（暗底适配）
- 卡片暗黑毛玻璃：bg-[#111115]/60 + backdrop-blur-xl + border-white/5
- 蓝色微光霓虹边缘：box-shadow: 0 0 40px rgba(37,99,235,0.15)
- 大圆角 20–28px：rounded-2xl / rounded-3xl
- 标签胶囊（rounded-full）：暗色底+发光蓝字，border蓝色微光
- Bento网格：已播作品(5列+大卡) / 待播作品(5列)
- Gallery无限横向滚动：自动轮播，悬浮暂停，双语标注
- Gallery全屏查看器：缩略图预览栏 + 侧边分类导航 + 下载按钮 + 键盘/触摸滑动

## 标签与徽章（Tags & Badges）

- 胶囊形状（rounded-full / pill）
- 暗色底+发光蓝字：background rgba(37,99,235,0.10)，color #60A5FA
- border: 1px solid rgba(37,99,235,0.15)
- letter-spacing: 0.06em（加宽字间距）
- 内容：✦ Idol News, 971028, Stage Focus, WinWin's Choice, Fan Project
- 同时用于Hero标签区和About/Profile资料标签

## 图标（Icons）

- strokeWidth 1.5 线性轻量图标
- 未激活：#9CA3AF（丝绸灰）
- 激活/Hover：#2563EB（静谧蓝）
- Hover带发光效果：filter: drop-shadow(0 0 8px rgba(37,99,235,0.5))

## 动效与交互

- Hero错落入场：Editorial Fade Up
- Hero视频弹出：pop-in动画
- Hero鼠标跟随：视频小人translate+3D rotate微偏移
- Hero视频播放完毕：淡出消失
- 导航下拉：hover展开，transition + opacity
- 卡片 hover：translateY(-6px) + 蓝色微光霓虹阴影 + 图片 scale(1.05) + 边框变蓝

## 设计禁忌

- 禁止使用白色/浅色背景——主背景必须为纯黑#0B0B0C
- 禁止使用深色粗阴影——只允许暗黑毛玻璃阴影和蓝色微光霓虹
- 禁止使用小圆角——卡片至少20px，标签pill形
- 禁止视频小人撑满屏幕——必须max-width 320px
- 禁止在黑色背景上使用低对比度文字——主文字必须#F3F4F6
- 禁止使用紫色
- 禁止Gallery子页显示外链
- 禁止Hero背景照片完全被遮罩覆盖——照片必须可见（暗化处理即可）
