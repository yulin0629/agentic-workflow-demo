---
on:
  workflow_dispatch:
  schedule: weekly on monday
permissions:
  contents: read
  issues: read
  pull-requests: read
safe-outputs:
  create-issue:
    max: 1
network: defaults
---

# 每週 Repo 健康週報

請每週彙整並開一個 issue，內容包含：

1. 本週新增／關閉的 issue 與合併的 PR 概況。
2. 仍卡關（open blockers）的項目與停滯過久的 PR。
3. 值得關注的趨勢與給維護者的下一步建議。

請條列清楚、附上相關 issue / pull request / commit 連結，並以正體中文撰寫。

如果這是手動觸發的測試執行，也請照樣產生一份目前 repository 健康狀態報告。
