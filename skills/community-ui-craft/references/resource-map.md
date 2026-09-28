# 资源地图：按任务找组件，而非按热度堆库

目录整理于 2026-09-28。链接是官方入口或作者源仓库；使用时打开目标组件页，确认当时版本与条款。不是永久价格/许可承诺。本技能包不打包这些项目的源码。

## 1. 基础控件与页面结构

| 资源 / 入口 | 适用场景与取得方法 | 集成选择 |
|---|---|---|
| [Radix Themes](https://www.radix-ui.com/themes/docs/overview/getting-started) | React 工作台/软件；按文档装包，引入 CSS，在根部使用 Theme，再取 Button、Dialog、Tabs 等 | 自带风格，统一 accent、gray、radius、scaling |
| [Radix Primitives](https://www.radix-ui.com/primitives/docs/overview/introduction) | React 弹层、选择器、滑杆等行为原语；从组件页取得安装项和示例 | 无样式行为层，需主题和状态样式 |
| [shadcn/ui](https://ui.shadcn.com/docs/installation) | React 产品与平台；匹配框架后用官方 CLI/registry 添加组件，保留生成源码 | 读已有 components.json、Tailwind 和基础库配置；不重复初始化整个项目 |
| [UIkit](https://getuikit.com/docs/introduction) | 原生 HTML/JS 页面；从官网指向的 npm/release 取得 CSS/JS，选 Modal、Tab、Accordion、Switcher 等 | 不需要 React；避免与已有全局 CSS 冲突 |
| [daisyUI](https://daisyui.com/docs/install/) | 已用 Tailwind 的 HTML、React 等页面；按当前官方插件安装方法取得组件 markup | CSS 组件不自动提供业务行为；检查键盘和状态逻辑 |
| [HyperUI](https://www.hyperui.dev/) | 内容区、商品、导航等布局起点；打开组件，复制 HTML/Tailwind 代码 | 是布局片段，不是自动处理数据、焦点的完整应用 |
| [TanStack Table](https://tanstack.com/table) | 复杂排序、筛选、分页表格；选对应框架 adapter 与官方示例 | Headless 行为，需要渲染和控件外观；不能当成现成主题表格 |
| [Element Plus](https://element-plus.org/en-US/) | Vue 3 管理平台；从官方指南安装，再从组件页取表单、表格、弹窗等示例 | 适合 Vue，不因需要一个动效而迁移到 React |

先检查项目已有组件库。成熟的现有库无需为追求新轮子全部替换。跨库补充特色效果通常可行，同时装两套完整基础 UI 体系容易增加冲突。

## 2. 视觉组件与动效

| 资源 / 入口 | 具体选什么 | 怎么取得和使用 |
|---|---|---|
| [React Bits](https://reactbits.dev/) · [源码](https://github.com/DavidHDev/react-bits) | 背景 Silk、ColorBends；文字 BlurText、RotatingText；卡片 GlareHover；交互 Ballpit，具体以组件页为准 | Preview→Code→依赖；选 JS/TS、CSS/Tailwind 版本，复制完整依赖和样式或用官网 registry；调整参数和触发 |
| [Magic UI](https://magicui.design/docs/components) | Border Beam、Magic Card、Text Animate、Animated Beam、Shimmer Button 等 | 按公开组件页安装；Pro 模板另算。光效只强调重要区域 |
| [Animate UI](https://animate-ui.com/docs) | 有进入退出反馈的 Accordion、Tabs、Dialog | 按当前 registry 的基础组件版本接入；适合对应 React 控件体系 |
| [Motion](https://motion.dev/docs/quick-start) | 选中指示、列表重排、展开/收起、进入退出、手势 | 有 JS/React 等接口，选择对应文档；同一 transform 不同时交给多个库 |
| [GSAP](https://gsap.com/docs/v3/) | 多元素时间轴、按行文字、SVG 路径、滚动叙事 | npm+官方示例；SplitText、DrawSVG 按实际版本导入；幻灯片用页面事件，长网页才用适用的滚动触发 |
| [Codrops](https://tympanus.net/codrops/hub/) | 图片切换、文字编排、章节过渡 | 具体教程→Demo→Code→作者 GitHub；取效果源码和依赖，按产品改结构 |
| [Uiverse](https://uiverse.io/) | 小型按钮、开关、loader、卡片细节 | 逐项看代码、类型、作者和许可；加 CSS scope，清理全局 reset，补键盘与减少动效 |
| [Swiper](https://swiperjs.com/get-started) | 触屏作品展示、产品画廊、必要的轮播 | 按原生/框架导入模块与 CSS；默认手动切换，接键盘/导航/触屏，不擅自自动切走信息；明确要求自动播放时才配置对应控制 |
| [PhotoSwipe](https://photoswipe.com/getting-started/) | 高清案例图、论文图、摄影图库 | 配置图片真实尺寸，本地打包 CSS/core；保留原图入口 |

React Bits 当前 [LICENSE](https://github.com/DavidHDev/react-bits/blob/main/LICENSE.md) 含 MIT + Commons Clause 条件，不能简称普通 MIT；应用中的使用和组件本身打包再分发要区分。本技能只提供来源与方法，不把其源码收进资源包。GSAP 使用 [官方许可](https://gsap.com/community/standard-license/)，也不要写成 MIT。

常用检索组合：背景搜 React Bits Silk / ColorBends；卡片搜 GlareHover / Magic Card / Border Beam；标题搜 GSAP SplitText lines mask；交互球搜 React Bits Ballpit；页面过渡搜 Codrops page transition Demo Code。比较实际代码与运行效果，不把 Showcase 当组件下载站。

可直接定位的具体入口（按题材选择，不要求全部使用）：[ColorBends](https://reactbits.dev/backgrounds/color-bends)、[BlurText](https://reactbits.dev/text-animations/blur-text)、[GlareHover](https://reactbits.dev/animations/glare-hover)、[Magnet](https://reactbits.dev/animations/magnet)。React Bits 官方仓库的 `src/content/` 是已使用过的 JS/CSS 来源；例如 `Backgrounds/ColorBends/`、`TextAnimations/BlurText/`、`Animations/GlareHover/`。使用前确认当前路径与依赖，保留同目录 CSS 和仓库许可；这提供下载定位，不固定每个项目的视觉方案。

## 3. 数据、3D 与创意画布

| 入口 | 适合拿什么 | 接入注意 |
|---|---|---|
| [ECharts Examples](https://echarts.apache.org/examples/en/index.html) · [示例源码](https://github.com/apache/echarts-examples) | 图表、tooltip、legend、dataZoom、联动与更新 | 在编辑器复制 option；用真实数组生成 series；运行库和示例分别记录来源 |
| [D3 Gallery](https://observablehq.com/@d3/gallery) · [入门](https://d3js.org/getting-started) | 关系网络、数据叙事、brush/zoom、科学图 | Notebook 依赖、data、viewof 和响应单元格需转宿主更新；每个示例许可单独核对 |
| [Three.js Examples](https://threejs.org/examples/) · [源码](https://github.com/mrdoob/three.js) | 模型、光照、材质、控制器、剖切 | 示例、addons、运行库匹配版本；GLB/HDR/纹理是额外资产，不能漏下载 |
| [p5 Examples](https://p5js.org/examples/) | 生成艺术、流场、波形、教学交互 | 转 instance mode；尺寸随容器更新；固定种子便于复现；离屏停止 draw |
| [OpenProcessing](https://openprocessing.org/) | 创意 sketch 的视觉参考与允许复用的源码 | 按单个作品的源码可见性和许可判断，不是全站可下载再分发 |
| [Mermaid](https://mermaid.js.org/intro/) | 流程图、状态图、时序图 | 按官方语法生成 SVG，再给具体节点加解释；汇报可构建期输出 SVG |
| [Reveal.js](https://revealjs.com/) | 幻灯片、讲者视图、Fragments、Auto-Animate | 按页面生命周期触发组件，不把幻灯片强行换成长滚动网站 |

[Bruno Simon folio-2025](https://github.com/brunosimon/folio-2025)、[craftzdog-homepage](https://github.com/craftzdog/craftzdog-homepage) 是完整作品源码入口，研究镜头与场景如何结合导航。它们不是小型 UI 插件；只需旋转模型时不用搬入开放世界。先按 README 跑通，再选取合适部分，保留资产许可。

## 4. 字体、图标与美术素材

| 来源 | 取得方式与适用内容 | 避免误用 |
|---|---|---|
| [Lucide](https://lucide.dev/) · [原生 JS 接法](https://lucide.dev/guide/lucide) | 选图标，取 SVG 或框架包；统一尺寸和线宽 | 图标按钮有可读名称，不混用多种描边风格 |
| [Phosphor](https://phosphoricons.com/) · [React 官方包](https://github.com/phosphor-icons/react) | 从同体系选择常用方向、导航、状态图标，比较 regular/bold/fill/duotone；按框架取包或官方 SVG | 字重和控件外观一起看，避免将极细描边误当成高级；不凭空手写图标替代现成资源 |
| [Google Fonts](https://fonts.google.com/) · [Noto CJK](https://github.com/notofonts/noto-cjk) | 官方下载/仓库取字体和许可，中文、拉丁、数字设合理 fallback | 中文子集覆盖当前文案和动态文字，不能搬别项目缺字的子集 |
| [Google Fonts 源文件](https://github.com/google/fonts/tree/main/ofl) | 选具体 family 目录，取 TTF/WOFF 文件与 OFL；如 [Bodoni Moda](https://github.com/google/fonts/tree/main/ofl/bodonimoda)、[站酷小薇](https://github.com/google/fonts/tree/main/ofl/zcoolxiaowei) 可用于合适的展示标题 | 两者只是取得方法的实例，不是艺术页面默认配对；正文和功能界面按任务选择 |
| [Wikimedia Commons](https://commons.wikimedia.org/) · [复用说明](https://commons.wikimedia.org/wiki/Commons:Reusing_content_outside_Wikimedia) | 搜索到具体 File 页，核对作者、原尺寸、来源、许可后取得原文件/合适缩略版本 | 各文件许可不同；同一艺术作品可能有不同版本、馆藏与照片，不沿用错误署名 |
| [Poly Haven](https://polyhaven.com/) · [许可](https://polyhaven.com/license) | 选 HDRI、材质、模型；按画布尺寸下载合适分辨率 | 资产与网站代码许可分开；小画布无需最高分辨率整套纹理 |
| [Kenney](https://kenney.nl/assets) · [说明](https://kenney.nl/support) | 取具体 UI/模型/图块包及许可 | 游戏资产不默认适合企业后台，保留包内说明 |
| 用户已有截图、视频封面、品牌图 | 从实际产品/用户文件取得；缩略图与详情图分别设尺寸 | 不虚构功能，不带入无关私人内容 |
| 摄影/插画平台，如 [Unsplash](https://unsplash.com/) | 打开具体资产页，核对作者、下载方式、当前用途许可 | 站内计划可不同；不把搜索缩略图或热链自动视为可用资产 |

找不到合适授权素材时，可使用用户允许的图像生成工具制作专属插画，并标为生成素材。位图不等于真实控件，透明 PNG 不等于 3D 模型；实际操作仍需要状态与模型逻辑。

## 5. 灵感不等于下载授权

[Mobbin](https://mobbin.com/) 适合研究移动端完整操作流程；设计师作品、品牌网站和 Showcase 适合研究构图。明确给出的 Code、组件包、可复用资产才进入工程。付费区、截图可见性与复用权利分别判断。

资源失效时从官方主页/仓库重新定位，不猜 CDN 地址然后声称已核实。不能联网时检查已有包、缓存原件和许可，明确未更新核查的来源。

## 6. 真正的原生软件入口

用户明确做原生应用时，从平台控件和示例取得实现，不下载网页 JSX 冒充原生：

- Android / Compose：[Material 3 官方实现与示例](https://developer.android.com/develop/ui/compose/designsystems/material3)。沿当前项目版本添加组件依赖，通过主题统一颜色、排版和形状。
- Apple 平台：[Human Interface Guidelines](https://developer.apple.com/design/human-interface-guidelines) 选择平台交互模式，再按项目的 SwiftUI/UIKit/AppKit 控件文档实现。设计资源与图标有各自的使用条件。
- Qt / QML：[Qt Quick Controls 类型目录](https://doc.qt.io/qt-6/qtquick-controls-qmlmodule.html) 选所需控件，匹配当前 Qt 版本、样式和项目许可。

这些路线借鉴相同的视觉组合方法，但组件取得、主题 API 和交付工具链不同。只要求网页手机原型时不引入完整原生工具链。
