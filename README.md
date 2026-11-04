# 大师赛档案静态站

本站保存已验收的网页成品，由 GitHub Pages 托管。

- 源码和本地数据维护：[fengmaker/LangRenSha](https://github.com/fengmaker/LangRenSha)
- 站点地址：<https://fengmaker.github.io/langrensha-site/>
- `site/` 只保存本次验收通过的完整公开站点。
- `site/data/manifest.json` 的 `build_id`、`snapshot_id` 标识当前版本。

日常更新在源码工作目录运行 `python website/sync_pages.py`。命令从本地已发布 API 增量导出，复用未变响应与图片，完成网页构建和验收后同步此仓库并推送 `main`。本仓库的 `site/` 或 Pages 工作流变更会自动部署；源码仓库推送只触发源码验收。

Pages 发布源设为 GitHub Actions。Actions 中保留 **Deploy static site to Pages → Run workflow → main** 手动入口，用于重新部署已有成品。

回退时，在 `main` 撤销有问题的独立成品提交（`git revert <提交SHA>`）并推送，会自动部署回退结果。该操作只回退网页，不改变本地正式数据或数据库发布。
