# CatNumMod的个人主页

本项目使用多个 HTML 页面和统一的 CSS 文件，部署到 GitHub Pages 后即可访问。

## 页面路径

- `/`：主页
- `/about/`：个人简介
- `/studynotes/`：学习内容
- `/studynotes/analysis/`：分析
- `/studynotes/algebra/`：代数
- `/studynotes/geometry/`：几何
- `/diary/`：日记目录
- `/diary/entry-01/` 等：单篇日记

## 上传 LaTeX 和 PDF 笔记

以分析为例：

1. 把 `limits.pdf` 和 `limits.tex` 放进 `studynotes/analysis/files/`。
2. 打开 `studynotes/analysis/index.html`，找到希望添加资料的条目（例如“资料存档”）。
3. 删除相应条目的“暂无内容”，在 `<div class="diary-item static-item">` 内的文字区域添加如下链接：

```html
<ul class="resource-links">
  <li><a href="files/limits.pdf" target="_blank" rel="noopener">极限笔记（PDF）↗</a></li>
  <li><a href="files/limits.tex" download>极限笔记（LaTeX 源码）↓</a></li>
</ul>
```

4. 将 PDF、TeX 和 HTML 改动提交到 GitHub，等待 GitHub Pages 更新。

如果 TeX 编译需要自定义样式、图片或参考文献，建议同时上传完整 LaTeX 项目 ZIP。

## 新增日记

1. 复制 `diary/entry-03/` 文件夹并命名为 `diary/entry-04/`。
2. 修改新文件夹中的 `index.html` 标题、日期和正文。
3. 在 `diary/index.html` 复制一行 `.diary-item` 链接，指向 `entry-04/`。
4. 提交并推送到 GitHub。

## GitHub Pages 发布方法

把此项目中的所有文件（尤其是根目录 `index.html`）上传到 `catnummod.github.io` 仓库根目录。

仓库设置中选择 **Settings → Pages → Build and deployment**：
- Source：`Deploy from a branch`
- Branch：`main`
- Folder：`/(root)`

推送更新后，Pages 会自动重新发布。

## 本地预览

在项目根目录运行：

```bash
python -m http.server 8000
```

然后浏览器访问 `http://localhost:8000/`。目录形式的网址应通过本地服务器测试，不建议仅双击 HTML 文件。

## 修改样式

所有页面使用 `assets/css/style.css`，学习专题页和日记页采用统一的简洁目录样式。
