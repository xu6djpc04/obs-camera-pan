# OBS 鏡頭平移

用 OBS 內建的 WebSocket，對攝影機來源做「數位平移／縮放」：可拖曳平移、追臉、自動縮放，轉場有緩動效果。

下載：到 [Releases](../../releases) 取得 `OBS_CameraPan.zip`。

## 使用方式

1. 解壓縮，雙擊 `OBS_CameraPan.exe`（不需安裝 Python）。
2. **先開 OBS Studio**，並啟用 WebSocket：`工具 → WebSocket 伺服器設定 → 勾選「啟用 WebSocket 伺服器」`，連接埠 `4455`。
3. 第一次連線會問 WebSocket 密碼（OBS 同一個視窗按「顯示連線資訊」可查）。可選擇記在 Windows 認證管理員。
4. 選「場景」與「來源」（攝影機所在的場景與來源），按「開始控制」，選「手動」或「追臉」。
5. 錄完按「停止並還原」再關閉，OBS 的取景會回到原本。

程式視窗裡的「設定說明」按鈕有更詳細的 OBS 端設定。OBS 沒設定好時，程式也會自動跳出說明。

## 注意

- 僅支援 Windows；需要 OBS Studio 28 以上（內建 WebSocket）。
- 程式只修改場景項目的「裁切」，不讀取、不儲存攝影機影像。
- exe 沒有數位簽章，Windows SmartScreen 可能跳出警告，請點「其他資訊 → 仍要執行」。部分防毒軟體可能誤判，這是 PyInstaller 打包程式的常見情形。
- 設定檔 `config.json`、記錄檔 `obs_camera_pan.log` 會產生在 exe 旁邊。
