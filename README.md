# LiveCache の web ページ

App Store への提出に**必須の URL 2 つ**（プライバシーポリシー・サポート）を置く場所。

```
index.html     トップ
support.html   サポート     ← App Store の「サポート URL」
privacy.html   プライバシー  ← App Store の「プライバシーポリシー URL」
terms.html     利用規約
_style.css     3 枚で使う 1 枚
.nojekyll      GitHub Pages に Jekyll を通させない印
```

## 中身の出どころ

**プライバシーポリシーと利用規約の本文は、アプリの画面から生成している**
（`app/(tabs)/settings/{privacy,terms}.tsx`）。2 か所に書くと必ずずれるため。
文面を直すときは**アプリ側を直してから**、生成し直すこと。

## 手元で見る

```bash
python3 -m http.server 8000 --directory site
# → http://localhost:8000
```

## 公開する（GitHub Pages）

アプリ本体のリポジトリとは**別の公開リポジトリ**に置く。本体には設計資料
（`docs/requirements.md`）が入っており、そちらは公開したくないため。

1. GitHub で公開リポジトリを作る（例: `livecache-site`）
2. この `site/` の**中身**をそのリポジトリの直下に置いて push
3. Settings → Pages → Source を `main` の `/ (root)` にする
4. 数分で `https://<ユーザー名>.github.io/livecache-site/` が開く

App Store Connect に入れる URL:

- プライバシーポリシー … `https://<ユーザー名>.github.io/livecache-site/privacy.html`
- サポート … `https://<ユーザー名>.github.io/livecache-site/support.html`

## 差し替えるところ

`support.html` と `index.html` の連絡先メールアドレス。いまは開発者のものが
入っているので、公開用の宛先を分けるなら書き換える。

## 置き場所

**ここが公開している唯一の置き場。** GitHub Pages がこのリポジトリの `main` を
そのまま出している（https://yutybass.github.io/livecache-site/）。

アプリのリポジトリ（`livecache`）にも同じものを写していた時期があるが、
2 つあると片方だけ直して**公開されていないのに直したつもり**になる。
写しは消したので、直すときは必ずここで直して push する。
