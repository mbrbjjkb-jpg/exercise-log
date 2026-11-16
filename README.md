# 運動記録（exercise-log）

運動した日をワンクリックで記録する、単一HTMLのWebアプリです。
データはこのリポジトリの `data/exercise.json` に GitHub 経由で保存されます。

## 使い方

1. アプリを開く（GitHub Pages の URL）
2. 初回だけ、画面の案内に従って GitHub の Fine-grained Personal Access Token を入力して接続する
   - Repository access は **このリポジトリ（exercise-log）だけ** を指定
   - Permissions → **Contents** を **Read and write** に設定
   - トークンは使う端末のブラウザ内（localStorage）にだけ保存されます
3. 運動したら大きなボタンを押すだけ。もう一度押すと取り消し
4. カレンダーの日付タップでも記録の付け直し・取り消しができます（押し忘れの修正用）

## 画面の内容

- 月カレンダー：運動した日が緑色、今日は枠付き
- 表示中の月の集計：運動した日数／していない日数／実施率
  （分母はその月の経過日数。ただし記録を始めた日より前は数えません）
- 年単位の集計：年ごとに運動した日数／していない日数／実施率
  （最初の年は記録を始めた日から、今年は今日までを数えます）

## データ形式

`data/exercise.json`：

```json
{ "version": 1, "days": ["2026-11-16"] }
```

`days` は運動した日の "YYYY-MM-DD" 一覧（昇順）です。
