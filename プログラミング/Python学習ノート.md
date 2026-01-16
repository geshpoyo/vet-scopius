

# プログラミングでの心得
- 8割デバッグに費やされる
- 自分で調べて解決する力
- コードのきれいさや処理速度は気にしない
- コードの書き方は覚えない（都度ググる
- コピペしてもいい、しかしコードの意味は理解する
- エラーは敵ではなく“情報”
- 小さく作って小さく直す
- 動くコードが正義
- 再現性を最優先にする
	- 同じ入力なら同じ結果
	- 同じ環境なら同じ動作
    - 同じ手順なら同じ成果
- 環境構築は資産
	- 仮想環境- requirements.txt
    - バージョン固定
    - 設定ファイルのバックアップ
- ログを残す習慣をつける
- “動かない理由”より“動く条件”を探す
- 人のコードを読むのは最強の学習
- 未来の自分は他人だと思え
- 動作確認はスキル
- 最適化は最後でいい
- 自動化できるところは自動化する
- “わからない”はスタート地点

# VS Code + Python 拡張で本格開発環境を作る手順

## 1. VS Code をインストール
公式サイトから入れる。

## 2. Python 拡張を追加
- Python
- Jupyter

## 3. 仮想環境を作成
python -m venv venv


## 4. VS Code に仮想環境を選択
左下の Python バージョンをクリックして venv を選ぶ。

## 5. ライブラリをインストール

pip install requests rich typer pyyaml watchdog

## 6. Jupyter Notebook を VS Code 内で実行
.ipynb を開くだけで動く。

## 7. 推奨構成
- VS Code
- Python + Jupyter 拡張
- venv
- requirements.txt
- Obsidian でノート管理
- GitHub でバージョン管理

# Pythonのリストについて

  

リストは、複数の値（データ）をまとめて管理できるデータ型です。 

Pythonでは、`[]`（角カッコ）で囲み、値をカンマで区切って書きます。

  

---

  

### リストの作り方・基本操作

  

```python

# リストの作成

fruits = ["りんご", "バナナ", "みかん"]

numbers = [1, 2, 3, 4, 5]



## 要素の取り出し（インデックスは0から）

print(fruits[0])  # りんご

print(numbers[2]) # 3

  

## 要素の変更

fruits[1] = "ぶどう"

print(fruits)  # ["りんご", "ぶどう", "みかん"]

  

## 要素の追加

fruits.append("もも")

print(fruits)  # ["りんご", "ぶどう", "みかん", "もも"]

  

## 要素の削除

fruits.remove("みかん")

print(fruits)  # ["りんご", "ぶどう", "もも"]

  

## リストの長さを調べる

print(len(fruits))  # 3

  

## for文で全要素を処理

for fruit in fruits:

    print(fruit)


``` 



## 括弧の種類と使い分け（Python・一般的なプログラミング）
- **( ) 丸括弧** … 関数、数式、タプル
- **[ ] 角括弧** … リスト、インデックス指定
- **{ } 波括弧** … 辞書、セット（集合）

Pythonではインデントでブロックを表現するため、波括弧{ }は使いませんが、辞書やセットの定義には使います。
  

```python

# 丸括弧（かっこ）: ( )

# ・関数の呼び出しや、数式のグループ化に使う

print("こんにちは")

result = (1 + 2) * 3

  

# 角括弧（かくかっこ）: [ ]

# ・リストや配列の作成、要素の参照に使う

fruits = ["りんご", "バナナ", "みかん"]

print(fruits[0])  # りんご

  

# 波括弧（なみかっこ）: { }

# ・辞書（ディクショナリ）や集合（セット）の作成に使う

person = {"name": "フタバ", "age": 18}

print(person["name"])  # フタバ

  

colors = {"赤", "青", "緑"}  # セット（集合）

  

# その他の使い分け

# ・if文やfor文などの制御構文では、Pythonでは丸括弧や波括弧は不要

# ・他の言語（C, Java, JavaScriptなど）では、波括弧{ }でブロックを囲むことが多い
```


## 比較演算子まとめ（Python）

  
プログラミングでの＝は数学と違って代入するという意味なので等しいとする場合は
「 == 」 と2つ書かないといけない

```python

# 等しい

a == b   # aとbが等しいときTrue

  

# 等しくない

a != b   # aとbが等しくないときTrue

  

# より大きい

a > b    # aがbより大きいときTrue

  

# より小さい

a < b    # aがbより小さいときTrue

  

# 以上（大きいまたは等しい）

a >= b   # aがb以上のときTrue

  

# 以下（小さいまたは等しい）

a <= b   # aがb以下のときTrue
```

## Pythonで「:（コロン）」を入れるタイミング

  
### ポイント

- **「:」は、その下にインデントしてブロックを書く合図**
- if, for, while, def, class などの直後に必ず「:」を付ける
- それ以外の普通の行には「:」は不要
```python

# if文、for文、while文、def（関数定義）、class（クラス定義）などの

# 「ブロック（かたまり）」が始まる行の最後に「:」を付けます。

  

# if文

if 条件式:

    # ここに条件がTrueのときの処理を書く

  

# for文

for 変数 in リスト:

    # ここに繰り返し処理を書く

  

# while文

while 条件式:

    # ここに繰り返し処理を書く

  

# 関数定義

def 関数名(引数):

    # ここに関数の処理を書く

  

# クラス定義

class クラス名:

    # ここにクラスの内容を書く

```

# dot . の解釈
**ドットで階層を書くのは Python だけ。  
他の言語は `/` や `\` を使う。**
[[言語別：ドット記法と階層の意味]]

# ポータブル版
### メリット

- **システムに影響を与えない**  
    インストール不要で、フォルダごとコピーして使えるため、他のBlender環境やシステム設定に影響を与えません。
- **複数バージョンの共存が簡単**  
    複数のBlenderバージョンを同時に使いたい場合、フォルダを分けて置くだけでOK。
- **アドオン開発やテストに最適**  
    Pythonスクリプトやアドオンの開発・テスト時に、環境を壊してもすぐに初期状態に戻せるので安心。
- **USBメモリ等で持ち運び可能**  
    USBや外付けドライブに入れて、どこでも同じ環境で作業できる。

### デメリット

- **自動アップデートやOS連携が弱い**  
    通常版のような自動アップデートや、OSの「開く」メニューとの連携はありません。
- **ユーザーデータ（設定やアドオン）がポータブル版のフォルダ内に保存される**  
    通常版と設定が分離されるため、既存の設定を引き継ぎたい場合は手動コピーが必要。

---
title: Pythonおすすめライブラリ一覧
tags: [python, library, automation, workflow]
created: 2026-01-15
---

# 🧠 万能系ライブラリ
- **pathlib**  
  ファイル操作の標準。`os` より直感的。

- **rich**  
  CLI の見た目を美しくする。

- **pydantic**  
  データ構造のバリデーション最強。

- **typer**  
  CLI ツールを爆速で作れる。

---

# 📁 ファイル処理・自動化
- **watchdog**  
  フォルダ監視 → 自動処理に最適。

- **shutil / send2trash**  
  ファイル移動・削除の安全版。

- **PyYAML**  
  Obsidian の YAML フロントマター操作に必須。

- **python-dotenv**  
  APIキーなどの環境変数管理。

---

# 📝 テキスト処理・ノート処理
- **regex**  
  標準の `re` より強力。SRT変換などに最適。

- **markdown-it-py**  
  Markdown をパースして構造化。

- **python-frontmatter**  
  Obsidian の YAML を読み書きするのに便利。

---

# 📊 データ分析・可視化
- **pandas**  
  データ処理の王様。

- **polars**  
  pandas の高速版。

- **matplotlib / seaborn**  
  グラフ描画の定番。

---

# 🌐 Web・API
- **requests**  
  API叩くならまずこれ。

- **httpx**  
  非同期対応の requests 進化版。

- **beautifulsoup4**  
  スクレイピングの定番。

---

# 🤖 AI / 機械学習
- **transformers**  
  自然言語処理の王道。

- **sentence-transformers**  
  埋め込み生成に最適。

- **scikit-learn**  
  機械学習の基礎。

---

# 🧪 ユーティリティ
- **tqdm**  
  進捗バー。

- **loguru**  
  ログ管理が劇的に楽。

- **python-slugify**  
  ファイル名を安全に整形。

---

# 🎯 talt向け最強セット（5つ）
あなたのワークフローに最適な組み合わせ。

- **pathlib**  
- **PyYAML**  
- **regex**  
- **typer**  
- **watchdog**

---


## データー型の種類


概要

Python は **動的型付け**で、<mark style="background: #FF5582A6;">変数に型宣言は不要</mark>。組み込みの基本型と標準ライブラリで提供される特殊型が豊富です。

基本スカラー型

- **int**：整数（任意精度）。
- **float**：浮動小数点数。
- **str**：Unicode 文字列。　文字列は"文字列"で囲わないといけない
- **bool**：`True` / `False`（`int` のサブタイプ）。　<mark style="background: #FFB86CA6;">二択の時に使う</mark>

（上記は数値や文字列操作の基本。初心者向け解説も参考になる）。

主要コンテナ型

- **list**：順序あり・可変。
- **tuple**：順序あり・不変（イミュータブル）。
- **dict**：キーと値のマッピング（ハッシュテーブル）。
- **set / frozenset**：重複なし集合（`frozenset` は不変）。

バイナリと特殊型

- **bytes / bytearray**：バイナリデータ。
- **NoneType**：`None`（値なしを表す）。
- **datetime** 系：日付・時刻（`datetime`, `date`, `time`, `timedelta`）は標準ライブラリで提供。

拡張と実務的注意

- **型ヒント（typing）** で静的解析が可能（`List[int]` 等）。
- **ユーザ定義クラス** や **collections（deque, Counter, namedtuple, defaultdict）** など用途別の型も豊富。
- 型変換や `isinstance()` でのチェックを適切に使うとバグを減らせます。




# 文字列の取り出し方

Python で文字列（`str`）から部分文字列を取り出す方法を、**基本 → 検索 → 分割 → 正規表現 → 応用**の順でまとめたチートシート。コードはそのままコピペして試せます。

--- 

ネットで引っ張ってきたデータを数値として計算するにはデータ型を変換する必用がある
例えば
ネットで引っ張ってきた文字列と数字の２３を足す場合
```
a = '100'
print(a+23)

```
これだと１００が文字列だから　文字列+23になってしまう
```
a = '100'
print(int(a)+23)

```
これで結果１２３になる
---

### 基本 インデックスとスライス

- **インデックス**（1文字取得）
```python
s = "Python"
print(s[0])   # 'P'
print(s[-1])  # 'n'

```

- **スライス**（範囲取得）
    
    s = "Hello, world" print
s = "Hello, world"
print(s[0:5])     # 'Hello'
print(s[7:])      # 'world'
print(s[:5])      # 'Hello'
print(s[::2])     # 'Hlo ol'
print(s[-5:-1])   # 'worl'


- **変数で範囲指定**
a, b = 2, 8
print(s[a:b])


検索して取り出す
- **存在確認**
    
    "world" in s # True
- **位置検索**
    
    i = s.find("world")   # 7  見つからなければ -1
 index は見つからないと例外を投げる


分割と分解
- **split**
	- line = "name,age,city"
	- parts = line.split(",")  # ['name','age','city']
- - **partition**
	- head, sep, tail = "a=b=c".partition("=")  # ('a', '=', 'b=c')
- リスト内包で抽出
	- words = "one two three".split()
	- first_letters = [w[0] for w in words]  # ['o','t','t']

正規表現で柔軟に抽出

- **単一マッチ**
	- import re
	- text = "ID: 12345, date: 2026-01-13"
	- m = re.search(r"ID:\s*(\d+)", text)
	- if m:
		- print(m.group(1))  # '12345'
- **複数マッチ**
- re.findall(r"\d+", "a1 b22 c333")  # ['1','22','333']
