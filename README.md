# The Celestial Odyssey · 星穹奥德赛

A solar system you can hold in your hand, typeset like an astronomy magazine. Drag, click and zoom your way between the star field and the editorial columns — no install, no build step.

一颗可以握在手里的太阳系，排版成一本天文杂志。拖拽、点击、缩放，在星穹与专栏之间自由穿行——无需安装，无需构建。

![Overview · 全景总览](.github/preview-overview.png)

Live · 在线体验：<https://sulongwooo.github.io/the_celestial_odyssey/>

---

## What it is · 这是什么

A WebGL-rendered, interactive atlas of the solar system: the Sun, the eight planets, the Moon and five dwarf planets (Ceres, Pluto, Haumea, Makemake and Eris), each placed in true orbital order with real texture maps. The visual language borrows from print magazines — an oversized masthead, editorial columns and an issue folio — instead of the usual dashboard-style infographic.

> 一个用 WebGL 渲染的太阳系互动画册：太阳、八大行星、月球与五颗矮行星（谷神星、冥王星、妊神星、鸟神星、阋神星）都按真实纹理与轨道次序排布。整体视觉参照印刷杂志——巨幅报头、专栏文章、页脚刊号，而不是常见的仪表盘式科普页。

## What you can do · 你能做什么

- **Overview / 全景俯瞰** — All bodies orbit slowly along their paths; scroll to zoom in, drag to change the viewing angle. / 所有天体沿轨道缓慢公转，滚轮拉近细看，拖拽改变视角。
- **Click a body / 点击天体** — The camera docks to the left of the frame while a feature column slides in on the right, with semi-major axis, surface temperature, orbital and rotational periods plus bilingual commentary. / 镜头自动停靠到画面左侧，右侧滑出该天体的特写专栏，含半长轴、表面温度、公转/自转周期与中英双语解说。
- **Observation console / 观测调校仪** — Toggle the star field, orbit lines, revolution and rotation; set the time scale with a slider (up to 3.0×). / 开关注释星空、轨道线与公转/自转，滑块控制时间流速（最高 3.0×）。
- **Bilingual / 双语切换** — Every section, the folio and all body entries ship in English and Chinese; press `T` to switch. / 整套版式、页脚署名、天体文案均为中英两套，按 `T` 切换。

### The feature column · 特写专栏

On click, the camera position is computed from the viewing frustum so the selected body sits clear of the panel; the remaining bodies and orbit lines fade out, leaving the layout to the data and the text.

> 点击天体后，镜头按视锥计算停靠到左侧，右侧滑出该天体的杂志式专栏；其余天体与轨道线同步淡出，把版面留给数据与文字。

![Feature column: Ceres · 特写专栏：谷神星](.github/preview-focus.png)

| Input · 操作 | Action · 功能 |
| --- | --- |
| Drag / 拖拽 | Orbit the camera / 旋转视角 |
| Scroll / 滚轮 | Zoom in / out / 拉近、拉远 |
| Click a body / 点击天体 | Open its feature column / 进入特写专栏 |
| Click empty space / 点击空白 | Return to the overview / 返回全景 |
| `←` / `→` | Previous / next body (focus mode only) / 上一个、下一个天体（仅特写状态） |
| `ESC` | Return to the overview / 返回全景 |
| `T` | Toggle English / Chinese / 中英文切换 |

## Run locally · 本地运行

**Option 1 / 方式一** — open `index.html` directly in a browser. / 直接双击 `index.html`。

**Option 2 / 方式二** — serve it over a static server (recommended: textures load more reliably). / 起一个静态服务（推荐，纹理加载更稳定）：

```bash
python3 -m http.server 8123
```

Then open <http://localhost:8123>. / 浏览器打开 <http://localhost:8123>。

## Project structure · 项目结构

```
the_celestial_odyssey/
├── index.html              # Page body: styles and logic inlined / 页面主体，样式与逻辑全部内联
├── assets/
│   ├── lib/                # Three.js r128 + OrbitControls, vendored (no CDN) / 本地化依赖，无需 CDN
│   └── textures/           # 20 texture maps: 2K bodies and the star field / 20 张 2K 天体纹理与星空背景
├── .github/                # README previews: overview and feature column / 预览图：全景与特写
├── LICENSE
└── 无用/                   # Archived drafts, git-ignored / 历史草稿，已加入 .gitignore
```

## Deploy to GitHub Pages · 部署到 GitHub Pages

1. In **Settings → Pages**, set Source to **Deploy from a branch**. / 在仓库 **Settings → Pages** 中，Source 选择 **Deploy from a branch**。
2. Pick branch `main` and folder `/ (root)`, then save. / 选择分支 `main` 与目录 `/ (root)`，保存。
3. After a minute or two, visit `https://<username>.github.io/the_celestial_odyssey/`. / 等待几分钟后访问 `https://<用户名>.github.io/the_celestial_odyssey/`。

The page is plain static files — no build step, no backend. / 页面为纯静态文件，无构建步骤、无后端依赖。

## Tech & credits · 技术与素材

- **Rendering / 渲染** — Three.js r128 + WebGL, plain JavaScript, no framework and no build tool. / Three.js r128 + WebGL，纯原生 JavaScript，无框架、无构建工具。
- **Type / 字体** — Cinzel, Cormorant Garamond, Space Grotesk and Noto Serif SC via Google Fonts; falls back to system serif/sans-serif fonts when offline. / 通过 Google Fonts 加载；离线时自动回退系统衬线/无衬线字体。
- **Dependencies / 依赖** — Three.js and OrbitControls are vendored under `assets/lib`, so the scene runs without a network connection. / three.js 与 OrbitControls 已放入 `assets/lib`，断网也能运行。
- **Textures & data / 贴图与数据** — NASA / JPL public data; textures from [Solar System Scope](https://www.solarsystemscope.com/textures/) (CC BY 4.0). / NASA / JPL 公开数据，纹理来自 Solar System Scope（CC BY 4.0）。

## License · 许可

MIT License © 2026 sulongwooo
