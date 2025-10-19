# shift-data

はるちゃん（ChatGPT）が読むためのシフト台帳です。
`shift.csv` を更新して GitHub に push すれば、Raw URL 経由で常に最新を参照できます。

## 使い方
1. `shift.csv` を編集（UTF-8 / カンマ区切り）
2. GitHub に push
3. `shift.csv` を開いて **Raw** をクリック → URL をコピー
   例: https://raw.githubusercontent.com/<username>/shift-data/main/shift.csv
4. はるちゃん設定ファイルに上記 Raw URL を登録

## CSV 仕様
- ヘッダー: `日付,曜日,シフト,始業,終業,メモ`
- 日付: `YYYY-MM-DD`（例: 2025-10-20）
- 時間: `HH:MM`（24時間制、例: 09:00）
- 夜勤など日付跨ぎ:
  - 終業 `00:00` は **翌日0時** を表す（＝前日からの夜勤終わり）
  - 明け休みは `シフト=夜勤（明け）`, `始業=00:00`, `終業=09:30` など表記
- 休み: `シフト=休み`, `始業/終業` は空欄または `-`

## 例
