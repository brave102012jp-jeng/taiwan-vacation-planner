# 台灣假期活動規劃

中南部藝文活動、音樂展演、獨立書店講座的假期規劃工具。

## 使用方式

直接開啟網頁即可：[taiwan-vacation-planner](https://你的帳號.github.io/taiwan-vacation-planner/)

- 左側篩選地區、場館類型、活動類型
- 月曆或清單瀏覽活動
- 勾選加入「待訪清單」，長期展覽可選擇造訪日期
- 待訪清單可拖拉排序、匯出 HTML 或 Google 日曆 (.ics)

## 檔案結構

```
index.html      網站主體（不常動）
events.json     活動資料（每週更新）
```

## 每週更新資料

1. 將新的 `events.json` 複製到此資料夾覆蓋舊檔
2. 推上 GitHub：

```bash
git add events.json
git commit -m "update events $(date +%Y-%m-%d)"
git push
```

## 資料格式

`events.json` 是一個陣列，每筆活動欄位如下：

| 欄位 | 說明 | 範例 |
|------|------|------|
| `id` | 唯一識別碼 | `"tnam-01"` |
| `name` | 活動名稱 | `"agnès b. 塗鴉藝術特展"` |
| `region` | 縣市 | `"臺南市"` |
| `venue` | 場館名稱 | `"臺南市美術館2館"` |
| `address` | 地址 | `"臺南市中西區忠義路二段1號"` |
| `types` | 活動類型陣列 | `["展覽", "特展"]` |
| `venueType` | 場館分類 | `"博物館/美術館"` |
| `startDate` | 開始日期 | `"2026-06-25"` |
| `endDate` | 結束日期 | `"2026-09-20"` |
| `time` | 開放時間 | `"10:00-18:00"` |
| `desc` | 簡介 | `"展於 I、J 展覽室..."` |
| `link` | 售票／官方網址 | `"https://..."` |
| `fbUrl` | FB 原文貼文網址 | `"https://www.facebook.com/..."` |

### venueType 九大分類

1. 博物館/美術館
2. 音樂廳/表演藝術
3. livehouse
4. 爵士酒吧
5. 音樂餐廳
6. 圖書館/文學館
7. 電影館
8. 獨立書店/書店
9. 季節性或大型活動

## 資料來源

Apify 爬蟲抓取各場館 Facebook 粉絲專頁貼文，每 1–2 週更新一次。
