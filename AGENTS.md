# 封面项目规则

- 未经用户采用、确认或使用的候选，不得进入 `assets/approved-covers/`、`references/cases/`、`references/approved-index.md` 或其他正例记录。
- 整批被驳回但无逐图理由时，只记录批次事实，不推断单图原因。
- 保留无关用户改动。按本次改动核对文件、引用和差异；凭据、私有素材与未采用候选不得提交。
- 每次完成项目变更后，精确暂存本次文件、commit 并 push 到 `origin/main`（用户要求本地草稿除外）。读回远端提交和关键文件，确认本地、origin/main 与 GitHub main 一致后报告完成。

## 文件落位（2026-10-17 用户要求）

- 所有产出只落在本项目目录里：候选图进 `outputs/<批次>/`，过程稿进 `work/<批次>/`，成品进 `outputs/<批次>/最终封面/`。不许往 `~/Downloads` 根目录或其他地方散落文件。
- 用 Gemini 网页生图时，抓原图要点「下载完整尺寸的图片」，这个动作**会额外往 `~/Downloads` 根目录落一份 `Gemini_Generated_Image_*.jpeg`**。每抓完一张就删掉这份副本，任务结束前复查 `~/Downloads` 根目录没有散图。
