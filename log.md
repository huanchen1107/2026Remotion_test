# Development Log

## 2026.05.15
> **備忘錄**
> 本專案已完全改用官方 **Claude Code** 搭配 `.env` 中的 `ANTHROPIC_API_KEY` 運作。
> 直接執行 `./cc.sh` 即可。

### 今日重點紀錄
1. **專案初始化**：執行 cleanAll.sh 完成環境重置。
2. **專案模版建立**：已成功建立並推送至 GitHub 儲存庫 `huanchen1107/ProjectTemplate2026-v2`。
3. **文件優化**：
    - 更新 `README.md`，詳盡描述 `cc.sh`, `startup.sh`, `ending.sh`, `initial.sh`, `cleanAll.sh` 的功能與用法.
    - 建立 `.env.bak` 模版，確保 API Key 不會被誤傳至 GitHub。
4. **Git 環境配置**：初始化 Git 並確保 `.gitignore` 正確排除 `.env` 文件。

### 技術結論
- 專案已準備好作為 2026 年的開發模版。
- 所有核心腳本均已具備詳細的文件說明，便於新專案快速啟動。

## 2026.05.19
> **備忘錄**
> 本專案已成功整合 React 視訊創作框架 **Remotion**，並配置了 **Agent Skills**。
> 使用 Claude Code, Gemini 或 Codex 時，代理會自動識別 Remotion 最佳實踐。

### 今日重點紀錄
1. **Remotion 專案架設**：
   - 於 `remotion/` 子目錄中成功使用 `create-video` 腳本建立官方 Hello World 動畫專案，並安裝完全部 node 依賴包。
2. **AI Agent Skills 配置 (Remotion 最佳實踐)**：
   - 使用 `skills` 引擎在系統全域 (`~/.agents/`)、專案根目錄 (`.agents/`)、以及 Remotion 子目錄 (`remotion/.agents/`) 下部署了 `remotion-best-practices` 代理技能。
   - 所有先進開發 AI（如 Claude Code, Codex, Gemini）將能自動讀取該規則進行高品質程式碼創作。
3. **核心框架整合與極簡化**：
   - 將 legacy 腳本 (`initial.sh` 與 `cleanAll.sh`) 完全整合入 `startup.sh` 作為內建函數，使根目錄維持極簡且易於管理。
   - 在 `ending.sh` 中更新對話歷史記錄收集路徑為 `utils/reconstruct_dialog.py`，保持根目錄精簡。
4. **模板同步**：
   - 已將上述所有精簡化改進與 Remotion 技能預載完整 force-push 至官方模板 `_ProjectTempate2026_StartEndShell.git`。

### 技術結論
- 當您需要在此專案中開發動畫時，建議使用 Claude/Gemini/Codex 直接對 `remotion/` 資料夾進行創作。
- 專案根目錄已建立最簡配置，具備最強大、安全的 AI 開發日誌與 key 過濾功能。

