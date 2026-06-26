---
on:
  workflow_run:
    workflows: ["CI Build & Test"]
    types: [completed]
    branches: [main]
permissions:
  contents: read
  actions: read
  issues: read
safe-outputs:
  create-issue:
    max: 1
network: defaults
---

# CI 失敗診斷醫生

當被監看的 CI workflow 失敗時，請：

1. 取得失敗的 job、step 與測試紀錄，找出最可能的根本原因。
2. 開一個 issue，清楚說明：失敗的測試／步驟、推測原因、建議的修正方向。
3. 附上相關 workflow run、commit、檔案或測試名稱連結，方便維護者快速定位。

若被監看的 CI workflow 成功或被取消，請不要建立 issue、不要執行任何輸出動作。

Issue 標題請以 `[ci-doctor] ` 開頭。內容請保持精簡、可執行，並以正體中文撰寫。
