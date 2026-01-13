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

   