# コミット・ブランチルール

## コミットメッセージ

[Conventional Commits](https://www.conventionalcommits.org/ja/v1.0.0/) に従います。

```
<type>(<scope>): <subject>

<body(任意)>

<footer(任意)>
```

### type

| type | 用途 |
| --- | --- |
| feat | 新機能 |
| fix | バグ修正 |
| docs | ドキュメントのみの変更 |
| style | 動作に影響しない整形(空白、セミコロン等) |
| refactor | 機能追加でもバグ修正でもないコード変更 |
| perf | パフォーマンス改善 |
| test | テストの追加・修正 |
| build | ビルド・依存関係の変更(package.json, app.json 等) |
| ci | CI/EAS 設定の変更 |
| chore | その他の雑務 |
| revert | コミットの取り消し |

### scope(任意)

変更対象を示す短い名前。例: `explore`, `home`, `router`, `deps`

### subject

- 日本語で書く
- 50文字程度まで、末尾に句点を付けない
- 「〜を追加」「〜を修正」など、何をしたかが分かる形にする

### 例

```
feat(explore): 種目一覧画面を追加
fix(router): タブ切り替え時にクラッシュする問題を修正
build(deps): expo-image を更新
```

破壊的変更は `type!:` とし、footer に `BREAKING CHANGE: 内容` を書く。

## コミットの粒度

- 1コミット = 1つの論理的な変更
- 動かない状態(lint / 型エラー)でコミットしない。コミット前に `npx expo lint` と `npx tsc --noEmit` を実行する
- 無関係な変更を混ぜない

## ブランチ

`main` に直接コミットせず、ブランチを切って PR を出す。

```
<type>/<短い説明>   例: feat/workout-log, fix/tab-crash
```

## PR

- タイトルはコミットメッセージと同じ形式
- 何を・なぜ変更したかを本文に書く
- マージは Squash merge を基本とする
