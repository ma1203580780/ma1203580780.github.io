# ma1203580780.github.io

主机根 `https://ma1203580780.github.io/` 的落地页。GitHub Pages 用 `main` 分支根目录直接发布，
`.nojekyll` 关闭 Jekyll 处理。

## 这一页的职责

只做一件事：把访问主机根的人送到站点首页 `https://ma1203580780.github.io/mind/`。

**跳转必须用 `<meta http-equiv="refresh">`，不要用 JavaScript。**

2026-10-05 全主机被 Google Safe Browsing 标为钓鱼/社会工程（SOCIAL_ENGINEERING），
本机 Chrome 名单里命中的表达式正好是主机根 `ma1203580780.github.io/`。而这一页此前
整页只有一个 `location.replace()` 脚本跳转——那是本主机上唯一位于「被标位置」的反常行为。
meta refresh 是搜索引擎明确支持的跳转方式，JS 跳转不是，所以换掉了。

## 这个仓库还是 Search Console 的验证落点

要验证 `https://ma1203580780.github.io/` 这个「网址前缀」资源，把 Google 给的
`googleXXXXXXXXXXXX.html` 直接放进本目录根，推送即可。它会被发布到
`https://ma1203580780.github.io/googleXXXXXXXXXXXX.html`。

验证通过后，Search Console 的「安全性问题」会列出 Google 具体标了哪些 URL。

背景与完整恢复步骤见工作区的 `docs/SAFE-BROWSING.md`。

## 推送

本机 `github.com:443` 不通，走 SSH 443 入口：

```sh
GIT_SSH_COMMAND="ssh -F <workspace>/.tools/ssh_config" \
  git push ssh://git@github-mind/ma1203580780/ma1203580780.github.io.git HEAD:main
```
