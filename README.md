# OKRA-Skills

OKRA の組織レシピから呼び出す **スキル（AI が実行する業務手順）** の公開リポジトリです。

OKRA のレシピは「いつ・誰に・何を呼びかけるか」を担い、このリポジトリのスキルは「AI が何をどの手順で行い、何を出力し、人が何を確認するか」を担います。レシピに埋め込まれたプロンプトがスキルの URL を指し、AI がそれを読んで実行します。

## 使い方

1. OKRA のレシピに載っているプロンプトを、AI エージェント（Codex など、GitHub 上のファイルを取得できるもの）に貼る。
2. 対象の資料（校閲コメント、取材の文字起こしなど）を添付する。
3. AI が該当スキルの `SKILL.md` を読み、その手順と出力形式に従って成果物を作る。
4. 成果物の末尾にある「人が確認すること」を確認してから、次の工程へ渡す。

チャット型の AI で URL を読めない場合は、`SKILL.md` の本文をプロンプトに貼り付けて使ってください。

## 構成

```
skills/
  <業種>/
    <業務名>/
      SKILL.md        # スキル本体（必須）
      references/     # 出力書式の見本など（必要な場合のみ）
templates/
  SKILL_TEMPLATE.md   # 新しいスキルを書くときの型
```

## スキル一覧

| 業種 | スキル | 業務 |
|---|---|---|
| publishing | [author-questions](skills/publishing/author-questions/SKILL.md) | 校閲・編集の指摘を、著者への確認事項の一覧と確認メールの下書きにまとめる |
| publishing | [style-check](skills/publishing/style-check/SKILL.md) | 原稿を用字用語集と照合し、表記ゆれの候補を箇所・現状・修正候補・該当ルールの表にする |
| publishing | [interview-notes](skills/publishing/interview-notes/SKILL.md) | 取材の文字起こしを話題別に整理し、要約・引用候補・追加質問を原文の位置つきで出す |
| publishing | [writer-brief](skills/publishing/writer-brief/SKILL.md) | 確定した企画と合意済みの条件から、外部ライターへの執筆依頼書を下書きする |
| publishing | [design-brief](skills/publishing/design-brief/SKILL.md) | 企画書と確定仕様から、装丁・図版の依頼書を必須・希望・未決に分けて下書きする |
| publishing | [progress-digest](skills/publishing/progress-digest/SKILL.md) | 担当別の進捗報告を共通形式にそろえ、工程別の状況・停滞理由・確認が必要な案件を一覧にする |
| publishing | [book-blurb](skills/publishing/book-blurb/SKILL.md) | 承認済み原稿と著者プロフィールから、欄の文字数に合わせた内容紹介・著者略歴を下書きする |
| publishing | [metadata-check](skills/publishing/metadata-check/SKILL.md) | 書誌マスタと注文書・商品ページ原稿を突き合わせ、書名・価格・発売日などの不一致を一覧にする |
| publishing | [store-visit-report](skills/publishing/store-visit-report/SKILL.md) | 書店訪問メモを要望・合意事項・宿題・次回確認事項に整理し、営業報告にする |
| publishing | [sns-posts](skills/publishing/sns-posts/SKILL.md) | 承認済みの内容紹介から、媒体・読者別の SNS 投稿文案を作る |

## スキルを書くときの作法

- **業務レベルで書く。** 特定の案件・書名・顧客名・担当者名・会社名を入れない。
- **添付された情報だけを使う。** 添付にない事実・数値・修正案を AI に補わせない。不明は「要確認」。
- **人が確認することを必ず出力の末尾に置く。** AI の出力を最終成果物にしない。
- **やらないことを明記する。** 送信・公開・外部サービスへの接続はスキルの範囲外。
- **パスワード・トークンをユーザーに求めない。**
- 個人情報・機密情報を含む例文や見本を置かない。

## 免責

各スキルは業務の手順を示すものであり、出力の正確さを保証するものではありません。成果物は必ず人が確認してから使ってください。

## ライセンス

未定（決まり次第ここに記載します）。それまでの利用については、リポジトリの Issue でお問い合わせください。
