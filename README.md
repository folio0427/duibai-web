# duibai-web

對白（Duibai）app 的法務文件託管站，透過 GitHub Pages 公開發布。

對白是一款以電影 / 影集為主題的交友 app（Folio 的姊妹作，但為獨立產品，獨立 Supabase 後端與帳號體系）。這個 repo 不是對白的行銷網站，唯一用途是提供 Apple App Store 審核與 Supabase `tos_versions` 表所需的、可公開查閱、免登入的法務頁面。

## 內容

- `index.html` — 首頁，列出全部 6 份文件（中/英文各一份）
- `legal/terms-zh/`、`legal/terms-en/` — 服務條款
- `legal/privacy-zh/`、`legal/privacy-en/` — 隱私權政策
- `legal/account-deletion-zh/`、`legal/account-deletion-en/` — 帳號刪除說明
- `assets/` — 對白 app icon、共用樣式表
- `llms.txt` — 給 LLM / 爬蟲讀取的站點索引

## 內容來源與更新方式

法務文件之定版文字來源為 `/Users/Max/dialogue/legal_draft/`（本機路徑，不在本 repo 中）下的 6 份 markdown 檔案：`terms_zh.md`、`terms_en.md`、`privacy_zh.md`、`privacy_en.md`、`account_deletion_zh.md`、`account_deletion_en.md`。本站的 HTML 頁面是這些 markdown 逐字轉換而成，不得自行改動文字內容；日後條款更新時，應先修改來源 markdown 定版，再重新轉換覆蓋對應的 `legal/*/index.html`。

## 技術說明

- 純靜態 HTML + 一份共用 CSS（`assets/legal.css`），無建置工具、無 JS 相依。
- 採用「資料夾 + index.html」結構做 clean URL（GitHub Pages 不會像 Cloudflare Pages 一樣自動把 `.html` 308 轉址，因此用資料夾結構取代 `.html` 副檔名網址）。
- 由 GitHub Pages 從 `main` 分支根目錄（`/`）部署。
