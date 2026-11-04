# 大师赛档案静态站

本站保存已验收的网页成品，由 GitHub Pages 托管。

- 源码和本地数据维护：[fengmaker/LangRenSha](https://github.com/fengmaker/LangRenSha)
- 站点地址：<https://fengmaker.github.io/langrensha-site/>
- `site/` 只放本次验收通过的公开静态成品。
- `site/data/manifest.json` 的 `build_id`、`snapshot_id` 标识本次发布。

推送成品后，在 Settings → Pages 将发布源设为 GitHub Actions；进入 Actions → Deploy static site to Pages → Run workflow → main，手动上线。源码仓库的推送不触发本站部署。

回退时，在 main 撤销有问题的独立成品提交（`git revert <提交SHA>`），推送后手动运行相同工作流。该操作只回退网页，不改变本地正式数据或数据库发布。
