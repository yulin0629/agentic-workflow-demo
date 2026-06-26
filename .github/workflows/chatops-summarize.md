---
on:
  issue_comment:
    types: [created]
permissions:
  contents: read
  issues: read
  pull-requests: read
safe-outputs:
  add-comment:
    max: 1
network: defaults
---

# ChatOps 摘要小幫手

當有人在 issue 或 pull request 留言中輸入指令 `/summarize` 時：

1. 閱讀此 issue（或 pull request）的完整討論串。
2. 整理出「目前共識、待決問題、下一步行動」三段重點。
3. 以留言回覆，並以正體中文呈現。

若觸發留言中沒有 `/summarize` 指令，請不要留言、不要執行任何輸出動作。
