# リバーシ遊技場

ブラウザですぐ遊べるリバーシ2本と、それを選ぶトップページのセットです。
ビルド不要の静的サイト（HTML / CSS / JavaScript のみ）なので、Vercel にそのまま公開できます。

| URL | 内容 |
| --- | --- |
| `/` | アプリ選択ページ |
| `/oni-fuku` | 鬼と福のリバーシ（CPU戦3段階・2人対戦・持ち時間・棋譜） |
| `/kinoko-takenoko` | きのこ vs たけのこ（追加ルール・必殺技・特殊マス・テーマ曲） |

## フォルダ構成

```
reversi-apps/
├── index.html                 アプリ選択ページ
├── assets/                    選択ページ用の石の画像
├── oni-fuku/index.html        鬼と福のリバーシ（1ファイル完結）
├── kinoko-takenoko/index.html きのこ vs たけのこ（1ファイル完結）
└── vercel.json                URL設定（/oni-fuku のように .html なしで開ける）
```

## GitHub に上げる

GitHub で空のリポジトリ（README なし）を作ってから、このフォルダで実行します。

```bash
git remote add origin https://github.com/excitingworld-hub/reversi-apps.git
git branch -M main
git push -u origin main
```

## Vercel で公開する

1. Vercel の **Add New → Project** で、上のリポジトリを Import する
2. Framework Preset は **Other**、Build Command と Output Directory は空のまま
3. **Deploy** を押す

以後は `main` に push するたびに自動で再公開されます。
CLI を使う場合は、このフォルダで `npx vercel`（本番は `npx vercel --prod`）でも公開できます。

## 注意点

- 「きのこ vs たけのこ」の **派閥総力戦（全体の勝敗集計）** は claude.ai 上で開いたときだけ動く機能です。Vercel 版では自動的に非表示になります。
- 設定（モード・ルール・音楽のオン/オフなど）は各ブラウザの localStorage に保存されます。
- 音楽はブラウザの決まりにより、「対局を始める」を押したあとに鳴り始めます。
