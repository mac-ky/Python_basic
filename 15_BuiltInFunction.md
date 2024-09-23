# 組み込み関数

## print関数
数値や文字列，変数などを出力する関数


```python
print("ローソン", "セブンイレブン", "ファミリーマート")  # 1行で表示される
print("サークルＫ")
```

    ローソン セブンイレブン ファミリーマート
    サークルＫ



```python
print("ローソン", "セブンイレブン", "ファミリーマート", sep="-")  # "-"で区切られる
print("サークルＫ")
```

    ローソン-セブンイレブン-ファミリーマート
    サークルＫ



```python
print("ローソン", "セブンイレブン", "ファミリーマート", sep="-", end="-")  # デフォルトではend="\n"(つまり改行)となっているがそれを"-"に変更
print("サークルＫ")
```

    ローソン-セブンイレブン-ファミリーマート-サークルＫ


## type関数
引数に渡したオブジェクトの型を返す．


```python
I = 5
F = 3.14
St = "Hello python!"
L = [5, 3.14, "Hello python!"]

print(type(I))
print(type(F))
print(type(St))
print(type(L))
```

    <class 'int'>
    <class 'float'>
    <class 'str'>
    <class 'list'>



```python
# is演算子との組み合わせ
I = 5
F = 3.14

print(type(I) is float)  # False
print(type(F) is float)  # True
```

    False
    True


## float関数
引数に渡した値を浮動小数点数に変換する．


```python
# String型
St_float = "3.14"

changed_St_float = float(St_float)

print(type(St_float))
print(type(changed_St_float))
```

    <class 'str'>
    <class 'float'>


ちなみに，ほとんどの小数は2進数で表そうとすると循環小数になるので，コンピュータの内部では近似値として表されている．



```python
print(0.1 * 2)  # 誤差は小さいので，0.2になる
print(0.1 * 3)  # 誤差が大きく，0.3とはならない
```

    0.2
    0.30000000000000004



```python
# したがって
print(0.1 * 2 == 0.2)
print(0.1 * 3 == 0.3)
```

    True
    False


## round関数
小数や整数を任意の値に丸める．


```python
print(round(3.1415, 2))
print(round(3.005, 2))
```

    3.14
    3.0



```python
# 第2引数を省略すると整数になる．
print(round(2.5))
print(round(3.501))
```

    2
    4



```python
# 第2引数に負の値を指定すると整数部の指定となる
print(round(1024, -1))  # 10の位に丸められる
```

    1020


## bool関数
引数に渡したオブジェクトがTrueかFalseかを判定する．


```python
# 正しい式，True，0以外の数値や要素のときはTrue
print(bool(2 > 1))
print(bool(True))
print(bool(1))
print(bool("Hello Python!"))
print(bool([1, 2, 3]))
```

    True
    True
    True
    True
    True



```python
# 誤った式，False，0，空の要素のときはFalse
print(bool(2 < 1))
print(bool(False))
print(bool(0))
print(bool(""))
print(bool([]))
```

    False
    False
    False
    False
    False


## len関数
様々なオブジェクトの要素数を返す．


```python
print(len("Hello Python!"))  # スペースも1文字
print(len([1,2,3,4]))  # リスト内の要素数
```

    13
    4


## sum関数
要素の合計値を返す．


```python
L_fibo = [0,1,1,2,3,5,8,13]
print(sum(L_fibo))  # 0+1+1+2+3+5+8+13
```

    33



```python
L_fibo = [0,1,1,2,3,5,8,13]
print(sum(L_fibo, 100))  # 0+1+1+2+3+5+8+13+100
```

    133


## max関数
オブジェクト内の要素の中で最大値を求める．


```python
L_fibo = [0,1,1,2,3,5,8,13]
print(max(L_fibo))  
```

    13



```python
language = ["Python", "JavaScript", "PHP"]
print(max(language))  # P > J and y > H
```

    Python



```python
language = ["Python", "JavaScript", "PHP"]
print(max(language, key=len))  # len("JavaScript") > len("Python") > len("PHP")
```

    JavaScript



```python
D = {"a": 3, "b": 2, "c": 1}

print(max(D))  # keyの最大値
print(max(D.values()))  # Valueの最大値
```

    c
    3


## min関数
オブジェクト内の要素の数で最小値を求める．


```python
L_fibo = [0,1,1,2,3,5,8,13]
print(min(L_fibo))  
```

    0



```python
language = ["Python", "JavaScript", "PHP"]
print(min(language))  # P > J
```

    JavaScript



```python
language = ["Python", "JavaScript", "PHP"]
print(min(language, key=len))  # len("JavaScript") > len("Python") > len("PHP")
```

    PHP



```python
D = {"a": 3, "b": 2, "c": 1}

print(min(D))  # keyの最小値
print(min(D.values()))  # Valueの最小値
```

    a
    1


## range関数
連続した整数値を要素に持つオブジェクトを作成する．
```python
range(start, stop, step)
```


```python
for i in range(4):
    print(i)
```

    0
    1
    2
    3



```python
for i in range(0, 100, 7):
    print(i)
```

    0
    7
    14
    21
    28
    35
    42
    49
    56
    63
    70
    77
    84
    91
    98



```python
# 3の倍数と3のつく数を集める
nabeatsu = [i for i in range(1, 40) if i % 3 == 0 or '3' in str(i)]
print(nabeatsu)

```

    [3, 6, 9, 12, 13, 15, 18, 21, 23, 24, 27, 30, 31, 32, 33, 34, 35, 36, 37, 38, 39]


## zip関数
複数のリストやタプルに入った要素をまとめたオブジェクトを作成する．


```python
last_name = ["石川", "金沢"]
first_name = ["太郎", "花子"]

print(zip(last_name, first_name))

for i in zip(last_name, first_name):
    print(i)
```

    <zip object at 0x10f56f6c0>
    ('石川', '太郎')
    ('金沢', '花子')



```python
last_name = ["石川", "金沢"]
first_name = ["太郎", "花子"]

for i, j in zip(last_name, first_name):
    print(i)
    print(j)
```

    石川
    太郎
    金沢
    花子



```python
last_name = ["石川", "金沢", "福井"]
first_name = ["太郎", "花子"]

for i, j in zip(last_name, first_name):  # 少ない方の要素数に合わせられる
    print(i)
    print(j)
```

    石川
    太郎
    金沢
    花子


## enumurate関数
リストやタプルの要素とインデックスをまとめたオブジェクトを作成する


```python
last_name = ["石川", "金沢", "福井"]

print(enumerate(last_name))

for i in enumerate(last_name):
    print(i)
```

    <enumerate object at 0x11801b300>
    (0, '石川')
    (1, '金沢')
    (2, '福井')



```python
last_name = ["石川", "金沢", "福井"]

print(enumerate(last_name))

for i, j in enumerate(last_name):
    print(i)
    print(j)
```

    <enumerate object at 0x118019b40>
    0
    石川
    1
    金沢
    2
    福井


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．
