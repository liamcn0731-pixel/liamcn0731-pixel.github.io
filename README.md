# Liam 的个人主页

用 [Fuwari](https://github.com/saicaca/fuwari) 和 Astro 搭建的中文个人主页。首页按时间显示文章，旅游、音乐、游戏和生活日记各有独立页面。

## 本地预览

项目使用 Node.js 24 LTS 和 pnpm 9.14.4。首次在另一台电脑上运行时，先安装 Node.js 24 LTS，再在项目目录执行：

```powershell
npm.cmd install -g pnpm@9.14.4
pnpm.cmd install --frozen-lockfile
pnpm.cmd dev
```

打开终端显示的本地地址。测试站内搜索时，先运行 `pnpm.cmd build`，再运行 `pnpm.cmd preview`。

## 发一篇文章

1. 在项目目录运行 `pnpm.cmd new-post my-first-trip`。文件会生成在 `src/content/posts/`。
2. 打开生成的 Markdown 文件，填写标题、发布日期和正文。把 `category` 写成 `旅游`、`音乐`、`游戏` 或 `生活日记`。
3. 要发布时将 `draft: true` 改为 `draft: false`。封面可以放在 `public/images/`，并在文章头部填写 `image: /images/文件名.webp`。
4. 提交文章与配图，推送到 `main`。GitHub Actions 会构建并发布到 [GitHub Pages](https://liamcn0731-pixel.github.io/)。

```powershell
git add src/content/posts/my-first-trip.md
git commit -m "添加旅行游记"
git push
```

使用配图时，把配图文件也加入同一次提交。可以在 [Actions](https://github.com/liamcn0731-pixel/liamcn0731-pixel.github.io/actions) 查看部署状态。公开仓库里可以查看已推送的 Markdown 源码，私人日记和未公开的照片请留在本地。

## 修改主页

- 站名、头像、主题色和 GitHub 链接在 `src/config.ts`。
- 关于页面的文字在 `src/content/spec/about.md`。
- 主题源自 Fuwari，授权见 [LICENSE](LICENSE)。横幅由 ImageGen 生成。
