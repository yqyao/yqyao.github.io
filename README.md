# 姚勇强 · 学术主页

基于 [Minimal Light](https://github.com/yaoyao-liu/minimal-light)，保留双栏学术布局，使用 Markdown 管理正文。模板版本：`1ea07f39518ac44644406380c83da6f89037c4fc`。模板原说明见 README.template.md。

## 经常修改的文件

| 文件 | 用途 |
| --- | --- |
| index.md | 简介、研究方向、经历、项目、教育、荣誉 |
| _includes/publications.md | 代表作图文区与其他论文折叠列表，直接用 Markdown 编辑 |
| _config.yml | 姓名、邮箱、学术链接、头像与部署配置 |
| assets/img/ | 头像和项目图片 |
| assets/files/ | 可公开的 PDF 简历 |
| private/待核实与补充.md | 尚需确认的信息和本轮编辑说明 |
| private/original-resume.tex | 原始 LaTeX 备份 |

## 添加项目

在 index.md 的项目栏目下添加：

```markdown
### 项目名称
**角色｜开始时间 — 结束时间**

- 问题与背景。
- 个人完成的技术工作。
- 有依据的成果数据。

[代码](https://github.com/你的用户名/项目)
```

图片写法：`![项目说明]({{ '/assets/img/project.jpg' | relative_url }})`。

## 本地预览

此版本是 Jekyll 源码，不能通过双击 index.md 预览完整主题。安装兼容 Ruby 与 Bundler 后：

```sh
bundle config set --local path vendor/bundle
bundle install
bundle exec jekyll serve
```

打开 http://127.0.0.1:4000 ，改完 Markdown 保存后自动重建。

## 发布到 GitHub Pages（当前尚未发布）

1. 在自己的 GitHub 账号创建 `yqyao.github.io` 仓库；若已经存在，请整合到原仓库，不要覆盖。
2. 将本目录作为仓库内容提交；private/ 为本地原稿与编辑笔记，已忽略，不要手动上传。
3. 将 _config.yml 的 url 设置为 `https://yqyao.github.io`，baseurl 保持空字符串。
4. 在 Settings → Pages 选择 Deploy from a branch，分支 main，目录 /(root)。
5. 也可以使用 resume 仓库：url 相同，baseurl 改为 /resume，网址变为 https://yqyao.github.io/resume/。
6. 后续修改 Markdown 并提交，GitHub Pages 自动重新生成网页。

当前未配置头像与 PDF，页面不会出现无效的下载链接。放入真实附件后，在 _config.yml 中启用 avatar / cv_link。

## 论文配图

图片存放在 assets/img/papers/，在 _includes/publications.md 中修改对应图片路径。点击缩略图可查看原图。图文展示保持完整作者列表；其余 11 篇论文可点击展开。来源与图片说明见 private/论文配图来源.md。

## 本次发布结构

main 分支保存可编辑的 Markdown 与模板；master 分支保存 Jekyll 生成的网页，沿用原博客的发布分支。旧博客文章目录保留。更新 main 后需重新构建并将生成文件同步到 master，或后续配置自动部署。
