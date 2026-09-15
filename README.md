# 🐍 贪吃蛇小游戏（纯前端静态网页）

一个用 HTML + CSS + JavaScript（Canvas）实现的贪吃蛇游戏，零依赖、单文件，可直接部署到 GitHub Pages 或 Vercel。

## ✨ 游戏功能

- 方向键 / WASD 控制方向，空格键暂停/继续
- 手机端支持滑动操作和虚拟方向键（自动显示）
- 实时计分、蛇身长度统计
- 最高分本地保存（localStorage）
- 吃到食物后逐渐加速，难度递增
- 精致的圆角蛇身、苹果食物、蛇眼朝向等细节渲染

## 📁 项目结构

```
snake-game/
├── index.html    # 游戏主文件（HTML + CSS + JS 全部内置）
├── README.md     # 项目说明（本文件）
└── .gitignore    # Git 忽略规则
```

## 🚀 部署方案：GitHub + Vercel

### 第一步：把项目上传到 GitHub

1. 注册/登录 [GitHub](https://github.com)
2. 点击右上角 **+** → **New repository**，仓库名填 `snake-game`，选择 **Public**，点击 **Create repository**
3. 在本项目文件夹内打开终端（命令行），依次执行：

```bash
git init
git add .
git commit -m "feat: 贪吃蛇小游戏"
git branch -M main
git remote add origin https://github.com/<你的用户名>/snake-game.git
git push -u origin main
```

> 没装 Git 的话，也可以在 GitHub 仓库页面点 **uploading an existing file** 直接把 `index.html` 等文件拖进去提交。

### 第二步：用 Vercel 部署上线

1. 打开 [vercel.com](https://vercel.com)，点击 **Sign Up**，选择 **Continue with GitHub** 用 GitHub 账号登录
2. 授权 Vercel 访问你的 GitHub 仓库
3. 点击 **Add New... → Project**，在列表中找到 `snake-game` 仓库，点击 **Import**
4. 框架预设（Framework Preset）保持 **Other** 即可（纯静态网页无需配置），直接点 **Deploy**
5. 等待约 10 秒部署完成，Vercel 会给你一个在线地址，形如：

```
https://snake-game-<你的用户名>.vercel.app
```

把这个链接提交给老师就完成了 ✅

### 以后更新代码怎么办？

每次修改代码后，只需：

```bash
git add .
git commit -m "update: 更新说明"
git push
```

Vercel 检测到 GitHub 仓库更新后会**自动重新部署**，无需任何手动操作。

## 🛠️ 本地运行

无需任何安装，直接双击 `index.html` 用浏览器打开即可开始游戏。

## 🧩 核心代码说明（作业讲解可用）

- **游戏循环**：`setInterval(step, speed)` 定时驱动，吃到食物后 `speed` 减小实现加速
- **碰撞检测**：蛇头越界（撞墙）或坐标与蛇身重合（撞自己）即游戏结束
- **方向控制**：`setDir()` 中禁止 180° 掉头，防止瞬间自撞
- **渲染**：Canvas 2D API 绘制棋盘、圆角蛇身（`arcTo` 实现圆角矩形）和食物

## 📄 License

MIT
