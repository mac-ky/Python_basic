# Pythonの基本事項
## プログラムの3つの基本構造
### 順次進行
プログラムが書かれている上から順に処理していく．


```python
print("Good morning")
print("Good afternoon")
print("Good evening")
```

    Good morning
    Good afternoon
    Good evening



```python
print("Good morning")
print("Good evening")
print("Good afternoon")
```

    Good morning
    Good evening
    Good afternoon


コメントアウト機能：
メモや注釈はコメント文として追加する．プログラムの先頭に"# "を入れる．
Macなら， command + /
Winなら，Ctrl + /


```python
# これは挨拶を表示するコードです
print("Good morning")
print("Good evening")
print("Good afternoon")
```

    Good morning
    Good evening
    Good afternoon


### 条件分岐
特定の条件のときはAという処理，そうでないときはBという処理をする．



```python
num = 551

if num==551:
    print('あるとき〜')

else:
    print('ないとき〜')
```

    あるとき〜


### 繰り返し
決まった回数や条件を満たすまで同じ処理を行う


```python
l = [1,2,3,4,5]

for i in l:
    print(i)
```

    1
    2
    3
    4
    5


## 変数
文字や数字などのデータを入れておくことができる．
- 代入：変数に数値やデータを入れること
- 参照：変数から数値やデータを取り出すこと
- 変数を宣言する：新たに変数を作ること
- 変数の初期化：初めて変数に数値やデータを代入する



```python
# greetingという変数に"おはよう"という単語を代入する
greeting = "おはよう"
print(greeting)
```

    おはよう


### PEP8における命名ルール
- アルファベット，数字，アンダースコアを組み合わせる．：単語を区切りたいときは，大文字orアンダースコアで
- 変数名の最初の文字を数字にするのはNG
- アルファベットの大文字と小文字は区別される．
- 予約語(すでに役割が決まっている単語(e.g., for, return))は使えない．


```python
# これはエラーになる
greeting-morning = "Good morning"
```


      Cell In[11], line 2
        greeting-morning = "Good morning"
        ^
    SyntaxError: cannot assign to expression here. Maybe you meant '==' instead of '='?




```python
# 大文字やアンダースコアで単語を区切る．
# 大文字と小文字は区別される．

greeting_morning = "おはよう"
GreetingMorning = "Good morning"

print(greeting_morning)
print(GreetingMorning)
```

    おはよう
    Good morning



```python
#  予約語は使えないのでエラーになる
return = "こんにちは"
```


      Cell In[21], line 2
        return = "こんにちは"
               ^
    SyntaxError: invalid syntax




```python
# 予約語かどうかを調べることができる．
import keyword

print(keyword.iskeyword('return'))  # returnは予約語
print(keyword.iskeyword('Return'))  # Returnは予約語ではない

```

    True
    False



```python
# ちなみに，組み込み関数かどうかを調べるなら，以下のコード

print('list' in dir(__builtins__))  # listは組み込み関数
print('List' in dir(__builtins__))  # Listは組み込み関数
```

    True
    False


### ID関数
変数の場所を指し示すことができる．
文字列や変数，変数など全てのオブジェクトには固有のIDが振り分けられる．


```python
a = 3
print(id(a))
b = a 
a = 20
print(id(b))  # 変数aと同じIDになる
print(id(a))  # 最初のaとは異なるIDになる
```

    4312200368
    4312200368
    4312200912


## データ型
変数に入れるデータの種類．
    - 動的型付け言語(e.g.,Python, Ruby, PHP, Javascript)ではデータ型を指定する必要はない．
    - 静的型付け言語(e.g., C言語, Java, Kotolin, Go言語)ではデータ型を指定する必要がある．
Pythonにおけるデータ型．
- 数値型
    - int型：整数
    - float型：小数
- String型：文字列
- bool型：TrueもしくはFalseのどちらかを持つ値．
- list型：複数の要素を格納できるデータ型．数値，文字列，リストそのものを入れておける．順番(インデックス)をつけて管理する
- tuple型：list型によく似ているが，一度代入した要素を書き換えることができない．要素の追加や削除もできない．
- 辞書型：1つの変数で複数の要素を管理できる点はlistやtupleと同じだが，インデックスで管理するのではなく，keyとvaluseをセットで管理する．数字や文字列はkeyに使えるがlistは使えない．
- set型：集合を扱う．複数の要素を管理できる．要素の削除，追加も可能で，集合演算ができる．重複した要素がないことと要素に順番がないことがlistとの違い．

### type関数でデータ型を確認することができる．


```python
# 数値型
I = 5
F = 3.14

print(type(I))
print(type(F))
```

    <class 'int'>
    <class 'float'>



```python
# String型
St = "Hello python!" # 文字列は"もしくは'でくくる必要がある．

print(type(St))
```

    <class 'str'>



```python
# bool型
a = 3
b = 8

B_01 = (a < b)  # "aはbより小さい"の真偽を検証
B_02 = (a == b)  # "aはbと等しい"の真偽を検証

print(B_01)
print(B_02)

print(type(B_01))
print(type(B_02))
```

    True
    False
    <class 'bool'>
    <class 'bool'>



```python
# list型
L = [5, 3.14, "Hello python!", (a < b)]

print(L)
print(type(L))
```

    [5, 3.14, 'Hello python!', True]
    <class 'list'>



```python
# tuple型
T = (5, 3.14, "Hello python!", (a < b))  # tuple型は丸カッコを使う．

print(T)
print(type(T))
```

    (5, 3.14, 'Hello python!', True)
    <class 'tuple'>



```python
# 辞書型
D = {"int": 3, "float": 3.14, "string": "Hello python!", "bool": (a < b), "list": [5, 3.14, "Hello python!", (a < b)]} 
# 波カッコとコロン，コンマ使う

print(D)

print(type(D))
```

    {'int': 3, 'float': 3.14, 'string': 'Hello python!', 'bool': True, 'list': [5, 3.14, 'Hello python!', True]}
    <class 'dict'>



```python
# set型
Se_1 = {5, 3.14, "Hello python!", (a < b)}
Se_2 = {5, "Hello world!", (a == b), 3.14, 5} 

print(Se_1)
print(Se_2)  # 重複した要素は無視して表示される．
print(type(Se_1))
print(type(Se_2))
```

    {True, 3.14, 'Hello python!', 5}
    {False, 'Hello world!', 3.14, 5}
    <class 'set'>
    <class 'set'>


### 各データ型には固有の機能(メソッド)が備わっている．

### データ型の変換
データ型を変換するための組み込み関数がいくつか用意されている．


```python
# tuple型
T = (5, 3.14, "Hello python!", (a < b))  

# list関数listにで変換する
changed_T = list(T)

print(T)
print(type(T))
print(changed_T)
print(type(changed_T))
```

    (5, 3.14, 'Hello python!', True)
    <class 'tuple'>
    [5, 3.14, 'Hello python!', True]
    <class 'list'>



```python
# list型
L = [5, 3.14, "Hello python!", (a < b)]

# tuple関数でtupleに変換する
changed_L = tuple(L)

print(L)
print(type(L))
print(changed_L)
print(type(changed_L))
```

    [5, 3.14, 'Hello python!', True]
    <class 'list'>
    (5, 3.14, 'Hello python!', True)
    <class 'tuple'>



```python
# String型
St = "Hello python!" 

# list関数listにで変換する
chaged_St = list(St)

print(chaged_St)
```

    ['H', 'e', 'l', 'l', 'o', ' ', 'p', 'y', 't', 'h', 'o', 'n', '!']



```python
# String型
St_int = "57"
St_float = "3.14"

# int関数とfloat関数で文字列を整数や小数に変換できる．
changed_St_int = int(St_int)
changed_St_float = float(St_float)

print(type(St_int))
print(type(changed_St_int))
print(type(St_int))
print(type(changed_St_int))
```

    <class 'str'>
    <class 'int'>
    <class 'str'>
    <class 'int'>



```python
# String型
St = "Hello python!" # 文字列は"もしくは'でくくる必要がある．

# これはエラーになる
changed_St = int(St)
```


    ---------------------------------------------------------------------------

    ValueError                                Traceback (most recent call last)

    Cell In[51], line 5
          2 St = "Hello python!" # 文字列は"もしくは'でくくる必要がある．
          4 # これはエラーになる
    ----> 5 changed_St = int(St)


    ValueError: invalid literal for int() with base 10: 'Hello python!'


## Pythonの計算
数値同士では四則演算ができる．
文字列同士では複数の文字列の結合や繰り返しができる


```python
# 数値同士の足し算
a = 1
b = 2

c = a + b

print(c)
print(type(c))

# ついでにfloat関数のおさらい
changed_c = float(c)

print(changed_c)
print(type(changed_c))
```

    3
    <class 'int'>
    3.0
    <class 'float'>



```python
# 文字列同士の足し算
St_1 = "Hello " 
St_2 = "python!" 

St = St_1 + St_2
print(St)
print(type(St))
```

    Hello python!
    <class 'str'>


Pythonでは異なるデータ型の計算はできない．


```python
a = 1
print(type(a))

St_1 = "Hello "
print(type(St_1))

# これはエラーになる
a_merged_St_1 = a + St_1
```

    <class 'int'>
    <class 'str'>



    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[75], line 8
          5 print(type(St_1))
          7 # これはエラーになる
    ----> 8 a_merged_St_1 = a + St_1


    TypeError: unsupported operand type(s) for +: 'int' and 'str'



```python
# 組み込み関数を使ってデータ型を変換するとエラーは回避できる
a = 1
print(type(a))

St_1 = "Hello "
print(type(St_1))

# これはエラーにならない
a_merged_St_1 = str(a) + St_1
```

    <class 'int'>
    <class 'str'>


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
