## 自然言語

基本的に日本語を使用する。

**例外**
以下のような場面では例外的に英語を使用する。
- コミットメッセージの prefix
- ブランチ名

## ブランチ

以下のように運用する。

- **main**: プロダクトとしてリリースするためのブランチ。
- **develop**: 開発ブランチ。コードが安定しリリース準備ができたら main へマージする。このブランチが最新バージョンとなる。
- **feature**: 機能を追加するためのブランチ。 develop から分岐し develop にプルリクエストし、マージする。
- **hotfix**: バグの修正など、プロダクトの動作に影響する問題を解決するためのブランチ。 develop から分岐し、 develop にプルリクエストし、マージする。

**note**: 基本的に main ブランチと develop ブランチでは一切の操作を行わない。何らかの変更を行う場合は必ずイシューを作成し、ブランチを生やす。

### feature ブランチと hotfix ブランチについて
feature ブランチと hotfix ブランチは以下のフォーマットで命名を行う。

- feature/{Issueの番号}_xxx
- hotfix/{Issueの番号}_yyy

例）
- feature/1_set_up_dev_environment
- feature/47_create_model
- hotfix/139_fix_layout

## コミットメッセージ

コミットメッセージには「prefix とその変更を行った理由」を記載する。
https://qiita.com/konatsu_p/items/dfe199ebe3a7d2010b3e

コミットメッセージには prefix を付ける。
prefix を統一するための外部アプリケーションとして [Semantic Pull Request](https://github.com/zeke/semantic-pull-requests) を導入する。

フォーマットは以下
`prefix: 理由、変更したこと`

**例**
- `feat: 学習の精度を向上させるために、xxxを変更`
- `fix: レイアウトの崩壊を直すために、yyyを修正`
- `docs: コミュニケーションを円滑にするために、zzzを変更`

### コミットの粒度について
コミットは細ければ細かいほど良いという認識で問題ない。
ここまで書いたコード・ここまで作った機能を失いたくないと思ったらコミットする

## マージ可能条件

少なくとも1人からの Approve を必要とする。
