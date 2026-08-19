# LiveCache — web

App Store への提出に必要な公開ページ。

| ファイル | 用途 |
|---|---|
| `index.html` | トップ |
| `support.html` | **サポート URL**（App Store 必須） |
| `privacy.html` | **プライバシーポリシー URL**（App Store 必須） |
| `terms.html` | 利用規約 |

## 元

**中身はアプリ本体のリポジトリで作っている。** ここは公開するための置き場で、
直接編集しない（次に流し込んだときに消える）。

規約とプライバシーポリシーの本文は、さらにアプリの画面
（`app/(tabs)/settings/{privacy,terms}.tsx`）から生成している。同じ文章を
2 か所に書くと必ずずれるため。
