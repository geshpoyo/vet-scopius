```
from turtle import *
shape("turtle")
forward(100)
done()
```

```
from turtle import *
shape("turtle")
for i in range(4)
forward(100)
left(90)
done()
```
- **`for` 文の末尾にコロンがない** → `for i in range(4):` が正しい。
- **インデントが必要** → `for` の内部は必ずインデントして書く（Pythonの構文ルール）。


基本ルール

- **コロン `:` の後は必ずインデントする**（例：`for i in ...:`）。
- Python の慣習は **スペース4つ**。PEP8 に従うと可読性が高い。
- 同じブロック内は **同じ幅で揃える**。ネストが深くなるほどインデントを増やす（通常は4の倍数）。

```
from turtle import *
shape("turtle")

# 正しいインデント
for i in range(4):
    forward(100)
    left(90)

done()

```

- **`i` はループ変数**で、`for` が繰り返すたびに `range(4)` の次の値が `i` に代入される。- つまり **「今何回目か」や「その回で使う値」を受け取るための名前** だよ。
    
    `range(4)` の振る舞い
    
    - `range(4)` は **0, 1, 2, 3** の順に値を返す。
    - よって `for i in range(4):` の各反復で `i` は順に `0` → `1` → `2` → `3` になる。
- もしループ変数を使わないとき

- 値を使わないなら慣習的に **`_`（アンダースコア）** を使う：
```
for _ in range(4):
    forward(100)
    left(90)
```