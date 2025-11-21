# story-to-video-pipeline

一個可重現的 PoC 範例：將小說段落自動化轉為分鏡、角色與場景圖片、語音敘述，並示範如何把生成的素材整合到短片（示範影片放在 YouTube）。本專案包含 prompt 範本、Dify workflow JSON 範例、以及 GitHub Pages demo。

目標
- 提供一套最小可行流程（MVP），讓創作者能把文字內容轉為視覺化素材並展示在網頁上。
- 容易複製、分支與改良，促成社群共創。

目錄
- `docs/` — GitHub Pages 靜態展示檔（index.html）。
- `prompts/` — Prompt 範本（劇本、分鏡、圖像 prompt、TTS）。
- `workflows/` — Dify / 工作流 JSON 範例（可匯入 Dify 或作為流程參考）。
- `assets/` — 小型示範圖片（若需大型影片請上傳到 YouTube 再嵌入）。
- `LICENSE` — 授權條款（MIT 範例）。
- `CONTRIBUTING.md` — 貢獻指南。

快速開始（3 步驟）
1. 建立一個 public GitHub repo（ex: `story-to-video-pipeline`），將本專案檔案推上。  
2. 啟用 GitHub Pages：Settings → Pages → Branch: `main` → Folder: `/docs`，Save，數分鐘後訪問 `https://<your-username>.github.io/<repo>/`。  
3. 上傳示範影片到 YouTube（建議 unlisted），把影片連結放到 `docs/index.html` 的 VIDEO_URL 欄位中，或放到 `assets/`（僅小檔案）。

如何貢獻
- 建議先 fork repo → 建分支 → PR。  
- 使用 Issues 報告問題、討論 prompt 改良、或提出新 workflow 範例。  
- 若要提交新大型素材，請使用外部媒體儲存（YouTube / S3）並在 README 中註明授權來源。

授權
- 程式碼與文本：MIT（見 LICENSE）。  
- 模型輸出與第三方素材：遵循原模型與素材提供者的商業授權與使用條款，並在 `README` 明確標示來源與授權情形。

聯絡
- 作者 / maintainer: a07272
