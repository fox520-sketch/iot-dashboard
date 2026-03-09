# IoT Dashboard

這是一個可直接部署到 **GitHub Pages** 的 MQTT IoT Dashboard。

## 功能

- MQTT 即時監控
- 溫濕度即時曲線圖
- 歷史資料表
- 最大 / 最小 / 平均統計
- CSV 匯出
- Broker 自動備援
- 離線偵測
- 危險閃爍警示
- 手機版 Dashboard
- 雙擊全螢幕模式

## 預設 MQTT 設定

- 主要 Broker: `broker-cn.emqx.io`
- 備援 Broker: `broker.emqx.io`

### Topics

- `/YVTC001/dht22/temp`
- `/YVTC001/dht22/humi`
- `/YVTC001/dht22/i`

## GitHub Pages 部署方式

1. 建立一個新的 GitHub Repository，例如 `iot-dashboard`
2. 上傳 `index.html` 到 repo 根目錄
3. 進入 **Settings → Pages**
4. 在 **Build and deployment** 中選擇 **Deploy from a branch**
5. Branch 選 `main`，資料夾選 `/root`
6. 儲存後，GitHub 會提供網站網址

網站網址通常會像這樣：

```text
https://你的帳號.github.io/iot-dashboard/
```

## 本機測試

直接用瀏覽器開啟 `index.html` 即可。

## 注意事項

- 網頁使用 `wss://` 連線 MQTT，適合 GitHub Pages 的 HTTPS 環境
- 若 `broker-cn.emqx.io` 無法連線，系統會自動切換到 `broker.emqx.io`
- 歷史資料儲存在瀏覽器頁面記憶體中，重新整理後會清空
- 頁面使用外部 CDN 載入 `mqtt.js` 與 `Chart.js`，需要可連外網路

## 建議 Repo 結構

```text
iot-dashboard/
├── index.html
└── README.md
```
