# 国の通知リンク集（非公式）

各省庁が公開している通知文書へのリンクを、宛先・改正の種類・添付資料の種類で探せるようにまとめた個人運営のサイトです。国が運営するものではありません。

- サイト本体：`docs/index.html`（GitHub Pages で `docs/` フォルダを公開）
- データ：`docs/data/notices.json`

## 収集元

| 省庁 | ページ |
|---|---|
| 厚生労働省 | [法令等データベースサービス 登載準備中の新着通知](https://www.mhlw.go.jp/hourei/new/tsuchi/newindex.html) |

厚生労働省のRSSは、利用条件でホームページの作成や再配布を断っているため使いません。

## データの形（notices.json の notices の1件）

| 項目 | 内容 |
|---|---|
| `id` | `mhlw-` ＋ PDFファイル名（例：`mhlw-T261002S0020`）。重複登録の判定に使う |
| `title` | 件名 |
| `docNumber` | 文書番号（例：`保発0930第5号`）。事務連絡は `事務連絡` |
| `issuedDate` | 発出日（`YYYY-MM-DD`） |
| `ministry` / `bureau` | 省庁 / 局 |
| `recipients` | 宛先区分の配列：`都道府県` `市区町村` `国の機関・関係団体` |
| `recipientsText` | 宛先の原文 |
| `revisionType` | `法律改正` `政令・省令改正` `告示改正` `運用・解釈の変更` `その他` |
| `effectiveDate` | 施行日・適用日（`YYYY-MM-DD`、不明なら空） |
| `fields` | 分野タグの配列 |
| `summary` | 2〜3文の概要 |
| `summaryBy` | `ai`（AI要約）または `manual` |
| `url` | 通知本文のURL |
| `attachments` | `{ name, type, url, inMain }` の配列。`inMain` は本文PDFに同じつづりならtrue |
| `memo` | メモ（公開されます） |
| `addedBy` | `auto`（定期タスク）または `manual` |
| `addedDate` | 登録日（`YYYY-MM-DD`）。30日以内は「新着」表示 |
| `detail` | `full`（宛先・要約まで登録）または `simple`（件名・文書番号・発出日・リンクのみの簡易登録。医薬品の個別の通知など） |

添付資料の種類：`通知本文` `新旧対照表` `改正後全文` `概要資料` `Q&A・疑義照会回答` `様式・記載例` `法令・告示の本文` `スケジュール` `参考資料`

## 出典と利用条件

通知の情報は各省庁のウェブサイトを出典とし、概要は出典をもとにAIが作成・加工したものです。
