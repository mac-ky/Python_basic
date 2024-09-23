# tuple型
リストとよく似ているが，要素の追加，変更，削除ができない点が異なる．：indexメソッドとcountメソッドしか用意されていない．

## タプルの作り方
丸括弧とコンマで記述する．


```python
T_university = ('Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu')
print(T_university)
print(type(T_university))
```

    ('Hokkaido', 'Tohoku', 'Tokyo', 'Nagoya', 'Kyoto', 'Osaka', 'Kyusyu')
    <class 'tuple'>


## タプルへのアクセス
タプルの要素にアクセスするときはインデックス番号を指定する．


```python
T_university = ('Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu')

# インデックスは0から順に振られている．
# 角括弧の中にインデックス番号を指定することでアクセスできる．
print(T_university[0])  # 1つ目の要素が表示される
print(T_university[3])  # 4つ目の要素が表示される
```

    Hokkaido
    Nagoya


タプルでは要素の追加，変更，削除ができない．


```python
# これはエラーになる．
T_university = ('Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu')

T_university[3] = 'Tsukuba'

print(T_university)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[229], line 4
          1 # これはエラーになる．
          2 T_university = ('Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu')
    ----> 4 T_university[3] = 'Tsukuba'
          6 print(T_university)


    TypeError: 'tuple' object does not support item assignment


## タプルのスライス
要素の取得では，開始位置と終了位置のインデックスを指定することができる．


```python
T_fibo = (0,1,1,2,3,5,8,13)

# インデックスを範囲で指定する
print(T_fibo[2:4])  # 2番目から4番目(4番目は含まない)
print(T_fibo[3:])  # 3番目以降
print(T_fibo[:1])  # 1番目まで(1番目は含まない)
```

    (1, 2)
    (2, 3, 5, 8, 13)
    (0,)



```python
T_fibo = (0,1,1,2,3,5,8,13)

# コロンを２つ重ねると，ステップして指定することができる．
print(T_fibo[::3])  # 2つ飛ばしで指定
print(T_fibo[::-2])  # 後ろから1つ飛ばしで指定
```

    (0, 2, 8)
    (13, 5, 2, 1)


## 多次元タプル
タプルの中にタプルを入れることができる


```python
T_university = (['Hokkaido','Tohoku'],['Tokyo','Nagoya'], ['Kyoto','Osaka'],['Kyusyu'])

print(T_university[1][0])  # 1つ目のリストの1番目の要素
```

    Tokyo


## タプルの足し算，掛け算


```python
T_fibo = (0,1,1,2,3,5,8,13)

# データ型を揃えると足し算が可能
T_fibo_append = T_fibo + (21,34)

print(T_fibo_append)
```

    (0, 1, 1, 2, 3, 5, 8, 13, 21, 34)



```python
T_fibo = (0,1,1,2,3,5,8,13)

# 掛け算によってリストの要素を繰り返すことができる
T_fibo_repeat = T_fibo * 2

print(T_fibo_repeat)
```

    (0, 1, 1, 2, 3, 5, 8, 13, 0, 1, 1, 2, 3, 5, 8, 13)


## タプルのメソッド・組み込み関数・演算子

indexメソッドで要素が何個目にあるか調べることができる．


```python
T_fibo = (0,1,1,2,3,5,8,13)

print(T_fibo.index(5))
print(T_fibo.index(1))
```

    5
    1


countメソッドで指定した要素がいくつあるかを取得することができる．


```python
T_fibo = (0,1,1,2,3,5,8,13)

print(T_fibo.count(1))
```

    2


in演算子でリストの中に指定した要素が含まれているかを判定する．


```python
T_university = ('Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu')

print('Osaka' in T_university)  # True
print('Kanazawa' in T_university)  # False
```

    True
    False


sorted関数でタプルの要素を並び替えることができる．


```python
T_fibo = (0,1,2,13,8,1,5,3)

print(sorted(T_fibo))  # reverse=Trueを指定すると大きい順に並び替えられる．
```

    [0, 1, 1, 2, 3, 5, 8, 13]


max関数/min関数でリスト内の要素の最大値/最小値を取得できる．



```python
T_fibo = (0,1,1,2,3,5,8,13)

print(max(T_fibo))
print(min(T_fibo))
```

    13
    0


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
