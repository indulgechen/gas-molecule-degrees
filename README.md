# 气体分子的自由度 · 3D 交互课件

用于大学物理「能量均分定理 · 理想气体的内能」章节的交互式演示。页面使用原生 Canvas 2D 绘制 3D 透视场景，不依赖任何外部库或网络资源，单个 `index.html` 即可离线运行。

![桌面端预览](assets/preview-desktop.png)

## 功能

- 四种分子模型：单原子、刚性双原子、非刚性双原子、刚性多原子
- 固定在世界原点的 `x / y / z` 坐标轴；坐标轴不随分子平移或转动
- 平动参数：`x / y / z` 三个质心坐标滑轨
- 转动参数：`θx / θy / θz`；按分子类型自动启用有效转动轴
- 振动参数：非刚性双原子的键长偏移 `Δr`
- 自动演示 / 手动调节双模式
- 分子尺寸滑轨：40%–200%，对单原子、双原子、多原子模型统一生效
- 分子小球、细键线与固定坐标轴组成的简洁显示风格
- 自由度对照表、`i = t + r + s`、`ε̄ = i/2 kT`、`U = i/2 νRT`
- 桌面端和手机端响应式布局

## 操作

- 鼠标拖动：旋转观察视角
- 鼠标滚轮：缩放视角
- 手机单指拖动：旋转观察视角
- 点击 `t / r / s` 色块：显示或隐藏对应运动
- 拖动参数滑轨：自动切换为手动模式
- “归零”按钮：将质心坐标恢复到坐标原点
- `1–4`：切换分子；`Space`：暂停/播放；`R`：重置视角；`G`：辅助标注

## 文件结构

```text
.
├── index.html
├── README.md
├── .nojekyll
└── assets
    ├── preview-desktop.png
    ├── preview-mobile.png
    └── preview-formula.png
```

## 本地预览

直接双击 `index.html`，或在当前目录启动一个静态服务器：

```bash
python -m http.server 8000
```

然后访问 `http://localhost:8000/`。

## 部署到 GitHub Pages

1. 新建一个 GitHub 仓库，例如 `gas-molecule-degrees`。
2. 将本目录中的 `index.html`、`README.md`、`.nojekyll` 和 `assets/` 上传到仓库根目录。
3. 打开仓库的 **Settings → Pages**。
4. 在 **Build and deployment** 中：
   - Source 选择 **Deploy from a branch**
   - Branch 选择 **main**，目录选择 **/(root)**
5. 点击 **Save**，等待约 1 分钟。
6. 访问：

```text
https://<你的用户名>.github.io/gas-molecule-degrees/
```

如果仓库名为 `<你的用户名>.github.io`，访问地址为：

```text
https://<你的用户名>.github.io/
```

## 兼容性

建议使用较新的 Chrome、Edge、Firefox 或 Safari。页面使用 Canvas 2D、CSS Grid/Flex 和 `color-mix()`，不支持 Internet Explorer。

## 内容依据

依据「12.5 能量均分定理 · 理想气体的内能」自由度表制作；表中“刚性多原子”按非线性分子计。非刚性双原子的 `s = 2` 对应振动的动能与势能两个自由度；经典理论下每个自由度平均贡献 `½kT`。
