# 个人主页（静态站，GitHub Pages）

纯 HTML + CSS，没有 Jekyll、没有构建步骤。改完直接 push 就上线。

```
index.html              首页：简介 / 三个代表作 / 科研经历 / 教育 / 技能 / 联系
research.html           研究兴趣 + 在推进的方向（含 multimodal perturbational cell-state modeling）
projects/brats.html     BraTS 分割：完整结果表 + 逐类分析
projects/viberepair.html VibeRepair+：检索框架 + 评估协议纠错
projects/scilit-rag.html 文献重排：dueling bandit + citation context
assets/style.css        全站样式（含深色模式）
assets/Yihang_Jiao_CV.pdf 简历（换新版直接覆盖同名文件）
assets/photo.svg        证件照占位图
.nojekyll               告诉 GitHub Pages 不要跑 Jekyll
```

## 部署（约 5 分钟）

1. 在 GitHub 新建仓库，名字必须是 `<你的用户名>.github.io`（例如 `yihangjiao.github.io`），public。
2. 在本目录下：

```bash
git init && git add -A && git commit -m "personal site" && git branch -M main && git remote add origin https://github.com/<用户名>/<用户名>.github.io.git && git push -u origin main
```

3. 仓库 Settings → Pages → Source 选 `Deploy from a branch`，branch 选 `main` / 根目录 `/`。
4. 一两分钟后访问 `https://<用户名>.github.io`。

以后改内容：编辑文件 → `git commit` → `git push`，几十秒后自动更新。

## 上线前要换掉的三处

- **照片**：把证件照存成 `assets/photo.jpg`，然后把 `index.html` 里的 `assets/photo.svg` 改成 `assets/photo.jpg`。
- **中文名**：`index.html` 里 `<h1>` 上方有注释，想加就写成 `Yihang Jiao (焦一航)` 这种形式。
- **`research.html` 里的 "Multimodal perturbational cell-state modeling"**：目前是我按你简历里的能力线索写的方向草稿，术语和范围都要你自己按真实想法改一遍——这段是套磁邮件里教授最会点进来看的一段。

## 可选补充

- 代码链接：BraTS / VibeRepair+ 如果有 GitHub repo，在对应项目页的 `.tags` 里加一个 `<a href="...">Code</a>`。
- PDF：项目报告（`Former_U_Net.pdf`、`VibRepair_Plus.pdf`）可以放进 `assets/`，在项目页顶部加 `[PDF]` 链接。
- 自定义域名：Settings → Pages → Custom domain，并在根目录加一个 `CNAME` 文件。
