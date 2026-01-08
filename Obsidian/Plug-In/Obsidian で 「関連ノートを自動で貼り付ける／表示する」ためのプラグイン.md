🧲 1. Dataview（最強の関連ノート自動表示）
あなたの運用なら まずこれが本命。
できること
• 	タグ・リンク・frontmatter を条件にして
関連ノートを自動で一覧表示
• 	MOC に「関連Evergreen」「関連BOAT」を自動生成
• 	ノート下部に「このノートにリンクしているノート」を表示
例：同じタグのノートを自動表示

こんな人に最適
• 	思考のネットワークを自動で可視化したい
• 	MOC を半自動化したい
• 	BOAT → Evergreen の流れを整理したい

🔗 2. Backlink Panel（標準機能）
プラグインではないけど、最も軽くて確実。
できること
• 	「このノートにリンクしているノート」を自動表示
• 	「未リンクの関連箇所」も表示（超便利）
使い方
右サイドバー → Backlinks（バックリンク）
こんな人に最適
• 	自動で関連ノートを拾いたい
• 	余計なプラグインを増やしたくない

🧠 3. Breadcrumbs（階層型の関連ノート）
あなたの MOC 構造と相性がいい。
できること
• 	上位MOC / 下位MOC / 隣接ノートを自動表示
• 	ノート間の階層構造を可視化
• 	MOC を「地図」として強化
こんな人に最適
• 	MOC を本格的に運用したい
• 	ノートの階層関係を自動で整理したい

🧩 4. Juggl（グラフビュー強化）
関連ノートを「貼り付ける」というより、
視覚的に関連を見たい人向け。
できること
• 	ノート同士の関係をリアルタイムで可視化
• 	グラフ上でノートを開く

🧷 5. Link Suggestion 系（自動で関連ノートを提案）
代表例
• 	Local Graph（標準）
• 	Contextual Typography
• 	Smart Connections（AI系）
できること
• 	ノートを書いているときに関連ノートを提案
• 	自動でリンク候補を出す

![[Pasted image 20260109074820.png]]

🧭 talt向けの最適解（結論）

あなたのワークフローなら **Dataview + Backlinks + Breadcrumbs** の3点セットが最強。

- Dataview → 自動一覧
- Backlinks → 自動逆リンク
- Breadcrumbs → MOCの階層構造

この3つで、  
**BOAT → Evergreen → MOC のネットワークが完全に自動化**される。



# 具体的な方法
## 🔗 Related Notes
```dataview
list from #evergreen
where contains(file.outlinks, this.file.link)
or contains(this.file.outlinks, file.link)
sort file.mtime desc
```
```dataview
list from "02_Evergreen"
sort file.name asc
```


---
up: [[知識体系 MOC]]
down:
  - [[関連Evergreen1]]
  - [[関連Evergreen2]]
same:
  - [[隣接Evergreen]]
---