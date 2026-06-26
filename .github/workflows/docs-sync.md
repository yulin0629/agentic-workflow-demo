---
on:
  workflow_dispatch:
  schedule: daily

permissions:
  contents: read
  issues: read
  pull-requests: read

safe-outputs:
  create-pull-request:
    max: 1
    title-prefix: "[docs] "
    labels: [documentation]

engine: copilot
tools:
  github:
---

# 文件同步小幫手

請每天執行：

1. 比對近期合併的程式碼變更與現有文件（README、docs/）。
2. 找出已過時或不一致的說明。
3. 開一個 Pull Request，提出必要的文件更新，並在描述中說明改了什麼、為什麼。

限制：
- 不要更動程式碼，只更新文件。
- 若沒有需要更新的文件，請不要建立 Pull Request，並輸出 no-op 說明。
- 文件內容與 PR 說明皆使用正體中文。

如果這是手動觸發的測試執行，也請照樣檢查目前 repository 的 README 與文件是否需要同步。
