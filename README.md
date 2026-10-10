# Zehao Fan — Personal Homepage (v2)

第二版英文个人主页。保留上一版的浅色背景、绿色强调色、衬线姓名和原照片，改为三个主要区域：个人介绍与联系入口、论文列表、教育与学术服务。

## 查看网页

解压后，用浏览器打开 `index.html`。`assets/` 需要与 `index.html` 放在同一目录下。

另行提供的 `Zehao_Fan_Homepage_v2_Preview.html` 是单文件离线预览：样式、照片与 CV 已内嵌；其中 CV 按钮会下载原始简历 PDF。正式部署请使用本 ZIP 中的目录，而不是离线预览文件。

## 第二版调整

- 将研究方向写入两段连贯的个人介绍，不再逐项搬运简历内容。
- 删除 Selected research 项目卡片、算法介绍、性能数字、评估展开项，以及 Looking ahead 等零碎标题。论文区仅保留题目、作者、状态和已有链接。
- 删除完整技能清单、重复的研究方向列表和单独的 Get in touch 区域；联系入口集中在首页。
- 教育与学术服务并列呈现，手机端依次排列。新增内嵌 SVG 图标，不需要图标字体、CDN 或 JavaScript。

## 文件结构

```text
ericfanexe.github.io/
├── index.html              # 网页内容；直接编辑即可
├── .nojekyll
├── .gitignore
├── README.md
└── assets/
    ├── style.css           # 样式及移动端规则
    ├── profile.jpg         # 沿用第一版的照片文件，未再修改
    ├── favicon.svg
    └── Zehao_Fan_CV.pdf    # 原始简历，未修改
```

## 内容编辑

`index.html` 中的 `ABOUT`、`PUBLICATIONS`、`BACKGROUND` 注释分别标记三个区域。简介可以作为网页文案直接调整；论文标题、作者顺序、发表状态和已有链接仍沿用原简历及第一版。

没有新增技能、实习经历、录用信息或论文内容。未推断暑期实习的年份、入职日期、地域或工作许可。博士条目使用在读状态，不把未来预计毕业日期呈现为已获得学位。

`assets/style.css` 顶部的 `:root` 包含颜色、字体和页面宽度。图标直接写在 HTML 内。只保留链接悬停和锚点平滑滚动，支持系统的减少动态效果设置。

替换简历或照片时，保留 `assets/Zehao_Fan_CV.pdf` 和 `assets/profile.jpg` 的文件名即可。完整技能和研究细节保留在原始 CV 中，没有从 PDF 中删除。

## 发布前确认

网页正文没有手机号，但原始 CV 仍含手机号。论文中在审稿件的标题、作者和状态仍会显示；需要公开前自行确认这些信息适合发布。本次没有创建仓库、推送更改或公开网站；旧版本未被覆盖。

以下 GitHub Pages 部署说明保留自第一版，原查阅日期为 2026-10-09；本次仅修改网页，没有重新核验外部链接或更新论文状态。

## 发布到 GitHub Pages

个人站点的仓库名应为 `<username>.github.io`；GitHub 文档要求用户名中的大写字母在该仓库名中改为小写。按简历所列账号，准备使用 `ericfanexe.github.io`。

1. 确认 GitHub 登录账号是你准备使用的账号，并检查是否已有 `ericfanexe.github.io` 仓库。没有时新建该仓库；使用 GitHub Free 的简单方式是创建公开仓库。
2. 将本目录**里面的文件**放到仓库 `main` 分支的根目录。不要上传 ZIP 本身，也不要再套一层 `ericfanexe.github.io/` 文件夹；仓库首页应直接看到 `index.html` 和 `assets/`。浏览器拖拽可能遗漏隐藏文件，需确保 `.nojekyll` 也在根目录；遗漏时可在 GitHub 中创建同名空文件。
3. 打开仓库 **Settings → Pages**，将 **Source** 设为 **Deploy from a branch**，分支选择 **main**，文件夹选择 **/(root)**，然后保存。
4. 等待部署工作流完成。正式地址应为 `https://ericfanexe.github.io/`，实际地址与发布结果以 Pages 设置页为准。GitHub 文档提示，推送后发布可能需要最多约 10 分钟。

**重要**：GitHub Pages 网站通常是公开可访问的，即使某些套餐允许源仓库为私有。不要把不打算公开的文件放入发布目录。

官方说明（2026-10-09 查阅）：

- [GitHub Pages quickstart](https://docs.github.com/en/pages/quickstart)
- [Creating a GitHub Pages site](https://docs.github.com/en/pages/getting-started-with-github-pages/creating-a-github-pages-site)
- [Configuring a publishing source](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)

## 本次检查

已使用 Chromium 检查 320、360、375、390、430、600、768、820、1024、1280、1440、1920 像素宽度的布局，未发现页面横向溢出。已检查站内锚点、重复 ID、资源相对路径、照片加载，以及离线预览的 CV 下载；下载文件与原 CV 字节一致。论文标题和作者顺序与第一版一致。

浏览器环境禁止 file URL 导航，因此渲染检查使用同一套 HTML/CSS 及内嵌资源；正式目录中的资源路径另行进行静态校验。这不等同于已完成线上部署测试。
