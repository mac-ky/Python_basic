# 繰り返し
決まった回数や条件を満たしていれば，同じ処理を実行する．

## for文
条件を満たしていれば同じ処理を繰り返す．カウンタ変数("i"が多い)で制御する．


```python
for i in [0,1,2,3,4,5]:
    print(i)
```

    0
    1
    2
    3
    4
    5



```python
for i in range(6):
    print(i)
```

    0
    1
    2
    3
    4
    5


## break
ある条件にあてはまったとき，繰り返し処理を終了させる


```python
for i in range(6):
    if i == 4:
        break  # iが4になったら処理を終了させる
    print(i)
```

    0
    1
    2
    3


## continue
ある条件にあてはまったとき，処理をスキップさせる．


```python
for i in range(6):
    if i == 4:
        continue  # iが4になったら処理をスキップ
    print(i)
```

    0
    1
    2
    3
    5


## for文のネスト
for文の中にfor文を入れる．


```python
for i in range(4): 
    for j in range(3):
        print(i,j ,sep="-")

```

    0-0
    0-1
    0-2
    1-0
    1-1
    1-2
    2-0
    2-1
    2-2
    3-0
    3-1
    3-2


## while文
処理を繰り返す条件を書き，条件を満たしている間処理を繰り返す．条件は決まっているが，繰り返す仮数が不明なときに有効．


```python
i = 0

while i < 6:
    print(i)
    i += 1
```

    0
    1
    2
    3
    4
    5



```python
i = 1

while i < 500:
    print(i)
    i *= 3
print("しゅーりょー")
```

    1
    3
    9
    27
    81
    243
    しゅーりょー


## 練習問題

### 数列の表示と和
フィボナッチ数列の初稿から第5項までを表示し，その和も計算


```python
n = 5
L_fibo = []

# フィボナッチ数列を求める
if n == 1:
    L_fibo = [0]
elif n == 2:
    L_fibo = [0, 1]
else:
    L_fibo = [0, 1]
    while len(L_fibo) < n:
        next_value = L_fibo[-1] + L_fibo[-2]
        L_fibo.append(next_value)

# 数列と和を表示
print(f"フィボナッチ数列の第{n}項まで: {L_fibo}")
print(f"その和: {sum(L_fibo)}")

```

    フィボナッチ数列の第5項まで: [0, 1, 1, 2, 3]
    その和: 7


### 素数の判定
変数numに入力した値が素数かどうかを判定


```python
num = 7

# 2以上の自然数でなければ素数ではない
if num < 2:
    print(f"{num}は素数ではありません")
else:
    # 2からnumの平方根までの範囲で割り切れるかを確認
    for i in range(2, int(num**0.5) + 1):
        if num % i == 0:
            print(f"{num}は素数ではありません")
            break
    else:
        print(f"{num}は素数です")

```

    7は素数です


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
