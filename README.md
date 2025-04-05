# cloud-native-hw2

這是雲原生課程的第二次作業，主要目的是練習使用 GitHub 的 Pull Request 機制，並了解 GitHub Actions 如何進行基本的自動化工作流程。

## Pull Request (PR)

在本專案中，透過實作 PR 的流程，可以練習協作開發中常見的操作方式。Pull Request 是一種將分支上的變更提交給主分支的方式，通常會伴隨代碼審查流程。

- 建立 PR：當分支上的功能開發完成後，可以透過建立 PR 的方式請求將變更合併至主分支。
- 進行審查：PR 建立後，其他開發者或自己可以針對提交內容進行檢查與討論。
- 完成合併：PR 經過審查並確認無誤後，可將其合併到主分支中，正式納入專案版本。

## GitHub Actions

GitHub Actions 是 GitHub 平台提供的自動化工具，可用於處理 CI/CD（持續整合與持續部署）相關工作。藉由設定工作流程，系統可以自動執行測試、建構等任務。

在此作業中，我們透過 GitHub Actions 設定一個簡單的自動化流程，讓每當 PR 被建立時，系統會自動執行特定檢查，例如程式輸出的驗證，並根據結果判斷是否通過。

### GitHub Actions 設定說明

1. 工作流程檔案放置於 `.github/workflows/` 目錄中，格式為 YAML。每個檔案代表一個工作流程。
2. 可設定觸發條件，例如在 push 或 pull request 發生時啟動流程。
3. 每個工作流程包含一系列的步驟，例如檢出程式碼、執行測試、比對結果等。

### 工作流程內容

- 執行測試：每當有 PR 建立時，系統會自動執行預先撰寫好的測試邏輯，確認程式是否如預期運作。
- 檢查輸出：本作業設計的測試會比對特定檔案的輸出內容，若輸出正確，則流程成功；若輸出不符，則流程會失敗。

## 如何查看 GitHub Actions 執行情況

1. 建立 PR 或推送代碼到指定分支時，GitHub Actions 會自動開始執行工作流程。
2. 點選 GitHub 頁面中的 "Actions" 分頁，可以查看每一次執行的詳細紀錄與結果，包括每個步驟是否成功執行。

## 參考資料

- GitHub Actions 說明文件：https://docs.github.com/en/actions
- Pull Request 教學：https://docs.github.com/en/github/collaborating-with-issues-and-pull-requests/about-pull-requests