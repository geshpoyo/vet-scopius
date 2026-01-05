```embed
title: "Obsidianを使ってGithub PagesのJekyllウェブサイトを更新する？ : r/ObsidianMD"
image: "https://id.rlcdn.com/472486.gif"
description: ""
url: "https://www.reddit.com/r/ObsidianMD/comments/1ift35f/using_obsidian_to_update_jekyll_website_for/?tl=ja"
favicon: ""
aspectRatio: "100"
```
Obsidian のノートはそのままでは Jekyll で動かない

Jekyll には **front matter（YAML）** が必要。

例：
```
---
layout: page
title: "タイトル"
---
```


Obsidian のノートにはこれがないので、  
**Jekyll 用に変換する必要がある**という話。

2. Obsidian のフォルダ構造と Jekyll のフォルダ構造は違う

Obsidian は自由なフォルダ構造だけど、  
Jekyll は厳密なルールがある。

例：

- `_posts/2025-01-06-title.md`
- `_pages/xxx.md`
- `_config.yml`

だから、**Obsidian の Vault をそのまま Jekyll に渡すと壊れる**。

3. どうやって同期するか？

スレッドではいくつかの方法が議論されている：

- GitHub Desktop
- Obsidian Git プラグイン
- 手動でコピー
- 自動スクリプト（PowerShell / Python）

つまり、  
**Obsidian → GitHub → Jekyll**  
の流れをどう作るか？という話。

4. Obsidian の Wikiリンク（`[[リンク]]`）は Jekyll では動かない

Jekyll は `[[リンク]]` を理解しないので、

- Markdown の `[text](url)` に変換する
- 変換スクリプトを使う
- プラグインを使う

などの議論がされている。

**talt が理解すべきポイントだけ抜き出すとこうなる**

1. Obsidian のノートはそのままでは Jekyll で動かない
2. Jekyll には front matter が必要
3. フォルダ構造も Jekyll 仕様に合わせる必要がある
4. Obsidian Git で同期するのは可能
5. ただし、変換ルールを決めないとサイトが壊れる