# 傳票掃描入庫 PWA

## 部署（放在現有的 GitHub Pages）
1. 在 `daska-` repo 裡新增資料夾 `slip/`，把這包檔案全部放進去（README 和 rules 可不放）。
2. 推上去後網址是：`https://fish33301.github.io/daska-/slip/`

## 接 Firebase（daska-f4811）
1. 打開 `index.html`，找到 `window.FIREBASE_CONFIG`，把 DASKA 庫存 app 裡的 `apiKey`、`messagingSenderId`、`appId` 貼上。
2. Firebase Console → Authentication → 登入方式 → 開啟「匿名」。
3. Firestore → 規則：把 `firestore.rules.txt` 的兩段**加進**現有規則（不要整份覆蓋）。
4. Authentication → 設定 → 已授權網域：確認有 `fish33301.github.io`。

沒填 config 也能用，資料會先存在手機本機；之後接上雲端會自動上傳。

## 手機安裝
- Android（Chrome）：打開網址 → 按頁面下方「安裝到手機」，或選單 →「加到主畫面」。
- iPhone（Safari）：分享 →「加入主畫面」。

## 資料位置（Firestore）
- `slip_days/{YYYY-MM-DD}`：該出貨日的傳票清單 `items[]`（code, size, note, t）
- `slip_config/sizes`：箱子尺寸清單

## 改版
改完 `index.html` 後，把 `sw.js` 裡的 `slip-scan-v1` 改成 `v2`，手機重開兩次就會更新。
