

![[Pasted image 20260111174422.png]]

yH9X0MZSA6i8c9Vonp
X90GnvvNgyEVlKa9kPw17z7z9ivSUFRi

https://ticktick-quick-add-obsidian-6yawfmvnj-mooshs-projects-0635287d.vercel.app

Obsidian
https://ticktick-quick-add-obsidian-6yawfmvnj-mooshs-projects-0635287d.vercel.ap

```embed
title: "GitHub - muxinli/ticktick-quick-add-obsidian: The TickTick Quick Add Obsidian Plugin lets you quickly create tasks in TickTick directly from your Obsidian notes."
image: ""
description: "The TickTick Quick Add Obsidian Plugin lets you quickly create tasks in TickTick directly from your Obsidian notes. - muxinli/ticktick-quick-add-obsidian"
url: "https://github.com/muxinli/ticktick-quick-add-obsidian?tab=readme-ov-file"
favicon: ""
```

## 1. 必要なもの

- Obsidian（コミュニティプラグイン ON）
- TickTick アカウント
- TickTick Developer Portal のアプリ
- Node.js（ビルド用）

## 2. Advanced URI をインストール

1. Obsidian → 設定
2. Community Plugins → Browse
3. **Advanced URI** を検索
4. Install → Enable

## 3. TickTick Quick Add プラグインを手動インストール

1. GitHub から ZIP をダウンロード  
    `https://github.com/muxinli/ticktick-quick-add-obsidian` (github.com in Bing)
2. ZIP を解凍
3. 解凍フォルダ内で Terminal / PowerShell を開く
4. 次を実行：

npm install 
npm run build

1. `main.js`, `manifest.json`, `styles.css` が生成される
2. それらを以下にコピー：

<YourVault>/.obsidian/plugins/ticktick-quickadd-plugin/

1. Obsidian → Settings → Community Plugins  
    → **TickTick Quick Add Plugin を有効化**

## 4. TickTick Developer Portal でアプリ作成

1. [https://developer.ticktick.com/](https://developer.ticktick.com/) にログイン
2. 「Create App」
3. App Name は自由
4. Redirect URI に以下を追加：

https://ticktick-quick-add-obsidian-6yawfmvnj-mooshs-projects-0635287d.vercel.app



1. 作成後、

- Client ID
- Client Secret  
    を控える

## 5. Obsidian 側で TickTick と接続

1. Obsidian → Settings → Community Plugins
2. TickTick Quick Add Plugin → Settings
3. Client ID / Client Secret を入力
4. 「Connect to TickTick」を押す
5. ブラウザで TickTick の認証を許可

## 6. ホットキー設定

1. Obsidian → Settings → Hotkeys
2. TickTick Quick Add Plugin の  
    **“Create TickTick Task from Paragraph”** にショートカットを割り当てる  
    例：`Ctrl + Alt + T`

## 7. 使い方

1. Obsidian の段落を選択
2. ホットキーを押す
3. 自動で：

- `#ticktick` が先頭に付く
- ブロックアンカー（^xxxx）が末尾に付く
- TickTick にタスクが作成される
- タスクに Obsidian の段落リンクが入る