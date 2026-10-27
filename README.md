# AlphaByteInc.github.io

アプリスタジオ AlphaByte（株式会社Alphabyte）の公開サイト。GitHub Pages（`main` ブランチ / ルート）で配信している。

- トップ: https://alphabyteinc.github.io/
- app-ads.txt: https://alphabyteinc.github.io/app-ads.txt
- 合格タイマー: https://alphabyteinc.github.io/goukaku-timer/
  - プライバシーポリシー: https://alphabyteinc.github.io/goukaku-timer/privacy.html
  - サポート: https://alphabyteinc.github.io/goukaku-timer/support.html
- 生成AIパスポート 問題集: https://alphabyteinc.github.io/genai-passport/
  - プライバシーポリシー: https://alphabyteinc.github.io/genai-passport/privacy.html
  - サポート: https://alphabyteinc.github.io/genai-passport/support.html
  - 特定商取引法に基づく表記: https://alphabyteinc.github.io/genai-passport/tokushoho.html
  - 正本は shikaku-quiz リポジトリの docs/legal/（1ファイル完結の HTML。assets/style.css は使わない）
- 統計検定2級 問題集: https://alphabyteinc.github.io/toukei2/
  - プライバシーポリシー: https://alphabyteinc.github.io/toukei2/privacy.html
  - サポート: https://alphabyteinc.github.io/toukei2/support.html
  - 特定商取引法に基づく表記: https://alphabyteinc.github.io/toukei2/tokushoho.html
  - 正本は shikaku-quiz-toukei2 リポジトリの docs/legal/（生成AIパスポート版と同じ1ファイル完結の HTML）
- G検定 問題集: https://alphabyteinc.github.io/gkentei/
  - プライバシーポリシー: https://alphabyteinc.github.io/gkentei/privacy.html
  - サポート: https://alphabyteinc.github.io/gkentei/support.html
  - 特定商取引法に基づく表記: https://alphabyteinc.github.io/gkentei/tokushoho.html
  - 正本は shikaku-quiz-gkentei リポジトリの docs/legal/（前2作と同じ1ファイル完結の HTML）
- アロマテラピー検定 問題集: https://alphabyteinc.github.io/aroma/
  - プライバシーポリシー: https://alphabyteinc.github.io/aroma/privacy.html
  - サポート: https://alphabyteinc.github.io/aroma/support.html
  - 特定商取引法に基づく表記: https://alphabyteinc.github.io/aroma/tokushoho.html
  - 正本は shikaku-quiz-aroma リポジトリの docs/legal/（先行3作と同じ1ファイル完結の HTML）

ビルド不要の静的 HTML。`.nojekyll` があるので Jekyll は通らない。

## 構成

```
index.html            スタジオのトップ（アプリ一覧）
app-ads.txt           AdMob 用。ドメイン直下にある必要がある
assets/style.css      全ページ共通のスタイル
<app-slug>/           アプリごとのページ
  index.html          アプリ紹介
  privacy.html        プライバシーポリシー
  support.html        サポート・FAQ
  icon.png            アイコン（512px）
```

## アプリを追加する

1. `goukaku-timer/` をコピーして `<app-slug>/` を作り、文面とアイコンを差し替える（CSS は `../assets/style.css` を参照）。
2. `index.html` の `<!-- APP: ... -->` ブロックを複製してカードを追加する。
3. AdMob を使うなら、そのアプリの publisher 行を `app-ads.txt` に追記する（同じアカウントなら追記不要）。
4. App Store Connect には、プライバシーポリシー URL `https://alphabyteinc.github.io/<app-slug>/privacy.html`、サポート URL `.../support.html`、デベロッパ Web サイト `https://alphabyteinc.github.io/` を入れる。

## 独自ドメインにする場合

例: `apps.alphabyte.co.jp` を CNAME で `alphabyteinc.github.io` に向け、リポジトリに `CNAME` ファイルを置いて Pages の Custom domain を設定する。
その場合、App Store Connect のデベロッパ Web サイトも新ドメインに変え、`app-ads.txt` がそのドメインの直下で返ることを確認すること。
