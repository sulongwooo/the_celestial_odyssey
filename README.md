# The Celestial Odyssey · 星穹奥德赛

一颗可以握在手里的太阳系，排版成一本天文杂志。打开网页即可拖拽、点击、缩放，在星穹与专栏之间自由穿行。

![全景总览](.github/preview-overview.png)

在线体验：<https://sulongwooo.github.io/the_celestial_odyssey/>

---

## 这是什么

一个用 WebGL 渲染的太阳系互动画册：太阳、八大行星、月球与五颗矮行星（谷神星、冥王星、妊神星、鸟神星、阋神星）都按真实纹理与轨道次序排布。整体视觉参照印刷杂志——巨幅报头、专栏文章、页脚刊号，而不是常见的仪表盘式科普页。

## 你可以做什么

- **全景俯瞰**：所有天体沿轨道缓慢公转，滚轮拉近细看，拖拽改变视角
- **点击天体**：镜头自动停靠到画面左侧，右侧滑出该天体的特写专栏（半长轴、表面温度、公转/自转周期 + 中英双语解说）
- **观测调校仪**：开关注释星空、轨道线与公转/自转，滑块控制时间流速（最高 3.0x）
- **双语切换**：整套版式、页脚署名、天体文案均为中英两套

### 特写专栏

点击天体后，镜头按视锥计算停靠到左侧，右侧滑出该天体的杂志式专栏；其余天体与轨道线同步淡出，把版面留给数据与文字。

![特写专栏：谷神星](.github/preview-focus.png)

| 操作 | 功能 |
| --- | --- |
| 拖拽 | 旋转视角 |
| 滚轮 | 拉近 / 拉远 |
| 点击天体 | 进入特写专栏 |
| 点击空白 | 返回全景 |
| `←` / `→` | 上一个 / 下一个天体（仅特写状态） |
| `ESC` | 返回全景 |
| `T` | 中英文切换 |

## 本地运行

方式一：直接双击 `index.html`。

方式二：起一个静态服务（推荐，纹理加载更稳定）：

```bash
python3 -m http.server 8123
```

浏览器打开 <http://localhost:8123>。

## 项目结构

```
the_celestial_odyssey/
├── index.html              # 页面主体，样式与逻辑全部内联
├── assets/
│   ├── lib/                # three.js r128 + OrbitControls（本地化，无需 CDN）
│   └── textures/           # 20 张 2K 天体纹理与星空背景
├── .github/                # 预览图：典藏全景 + 特写专栏
├── LICENSE
└── 无用/                   # 历史草稿，已加入 .gitignore，不会进入仓库
```

## 部署到 GitHub Pages

1. 在仓库 **Settings → Pages** 中，Source 选择 **Deploy from a branch**
2. Branch 选 `main`，目录选 `/ (root)`，保存
3. 几分钟后访问 `https://<用户名>.github.io/the_celestial_odyssey/`

页面为纯静态文件，无构建步骤、无后端依赖。

## 技术与素材

- **渲染**：Three.js r128 + WebGL，纯原生 JavaScript，无框架、无构建工具
- **字体**：Cinzel / Cormorant Garamond / Space Grotesk / Noto Serif SC（Google Fonts 在线加载；离线时自动回退系统衬线/无衬线字体）
- **依赖**：three.js 与 OrbitControls 已放入 `assets/lib`，断网也能运行
- **贴图与数据**：NASA / JPL 公开数据，纹理来自 [Solar System Scope](https://www.solarsystemscope.com/textures/)（CC BY 4.0）

## License

MIT License © 2026 sulongwooo
