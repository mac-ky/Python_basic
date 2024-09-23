# list型
Pythonでよく使われるデータ型の一つで複数のデータを格納することができる．

## リストの作り方
角括弧とコンマで記述する．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']
print(L_university)
print(type(L_university))
```

    ['Hokkaido', 'Tohoku', 'Tokyo', 'Nagoya', 'Kyoto', 'Osaka', 'Kyusyu']
    <class 'list'>


## リストの要素の変更
リストの要素にアクセスするときはインデックス番号を指定する．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

# インデックスは0から順に振られている．
# 角括弧の中にインデックス番号を指定することでアクセスできる．
print(L_university[0])  # 1つ目の要素が表示される
print(L_university[3])  # 4つ目の要素が表示される
```

    Hokkaido
    Nagoya



```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

# インデックス番号を指定して，要素を変更する
L_university[3] = 'Tsukuba'

print(L_university)
```

    ['Hokkaido', 'Tohoku', 'Tokyo', 'Tsukuba', 'Kyoto', 'Osaka', 'Kyusyu']



```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

# インデックス番号の値をマイナスにすると，後ろから数えた順番になる
L_university[-2] = 'Kobe'

print(L_university)
```

    ['Hokkaido', 'Tohoku', 'Tokyo', 'Nagoya', 'Kyoto', 'Kobe', 'Kyusyu']



```python
L_fibo = [0,1,1,2,3,5,8,13]

# インデックスを範囲で指定する
print(L_fibo[2:4])  # 2番目から4番目(4番目は含まない)
print(L_fibo[3:])  # 3番目以降
print(L_fibo[:1])  # 1番目まで(1番目は含まない)
```

    [1, 2]
    [2, 3, 5, 8, 13]
    [0]



```python
L_fibo = [0,1,1,2,3,5,8,13]

# コロンを２つ重ねると，ステップして指定することができる．
print(L_fibo[::3])  # 2つ飛ばしで指定
print(L_fibo[::-2])  # 後ろから1つ飛ばしで指定
```

    [0, 2, 8]
    [13, 5, 2, 1]


### リストのネスト
リストの中にリストを入れることができる


```python
L_university = [['Hokkaido','Tohoku'],['Tokyo','Nagoya'], ['Kyoto','Osaka'],['Kyusyu']]

print(L_university[1][0])  # 1つ目のリストの1番目の要素
```

    Tokyo


## リストの足し算，掛け算


```python
L_fibo = [0,1,1,2,3,5,8,13]

# データ型を揃えると足し算が可能
L_fibo_append = L_fibo + [21]

print(L_fibo_append)
```

    [0, 1, 1, 2, 3, 5, 8, 13, 21]



```python
L_fibo = [0,1,1,2,3,5,8,13]

# データ型がそろっていないとエラーになる．
L_fibo_append = L_fibo + 21

print(L_fibo_append)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[138], line 4
          1 L_fibo = [0,1,1,2,3,5,8,13]
          3 # データ型がそろっていないとエラーになる．
    ----> 4 L_fibo_append = L_fibo + 21
          6 print(L_fibo_append)


    TypeError: can only concatenate list (not "int") to list



```python
L_fibo = [0,1,1,2,3,5,8,13]

# 掛け算によってリストの要素を繰り返すことができる
L_fibo_repeat = L_fibo * 2

print(L_fibo_repeat)
```

    [0, 1, 1, 2, 3, 5, 8, 13, 0, 1, 1, 2, 3, 5, 8, 13]


## リストのメソッド・組み込み関数・演算子

appendメソッドはリストに要素を追加することができる．


```python
L_fibo = [0,1,1,2,3,5,8,13]

L_fibo.append([21,34])
print(L_fibo)
```

    [0, 1, 1, 2, 3, 5, 8, 13, [21, 34]]


extendメソッドではリスト内のデータを分解して要素として末尾に追加できる．


```python
L_fibo = [0,1,1,2,3,5,8,13]

L_fibo.extend([21,34])
print(L_fibo)
```

    [0, 1, 1, 2, 3, 5, 8, 13, 21, 34]


insertメソッドを使うとリストの指定した位置に要素を追加することができる．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

# インデックスと追加したい要素を指定する．
L_university.insert(4, 'Kanazawa')

print(L_university)
```

    ['Hokkaido', 'Tohoku', 'Tokyo', 'Nagoya', 'Kanazawa', 'Kyoto', 'Osaka', 'Kyusyu']


del文を使用してリストの要素を削除する


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

# 削除したい要素のインデックスを指定する．
del L_university[3]

print(L_university)
```

    ['Hokkaido', 'Tohoku', 'Tokyo', 'Kyoto', 'Osaka', 'Kyusyu']


popメソッドを使うと，リストを削除し，削除した要素を表示することができる．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

# 丸括弧の中でインデックスを指定する．
print(L_university.pop(3))

print(L_university)
```

    Nagoya
    ['Hokkaido', 'Tohoku', 'Tokyo', 'Kyoto', 'Osaka', 'Kyusyu']


removeメソッドを使うと指定した要素を検索し，削除することができる．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

L_university.remove('Tohoku')

print(L_university)
```

    ['Hokkaido', 'Tokyo', 'Nagoya', 'Kyoto', 'Osaka', 'Kyusyu']


clearメソッドでリストの全ての要素を削除することができる．


```python
L_fibo = [0,1,1,2,3,5,8,13]

L_fibo.clear()

print(L_fibo)
```

    []


in演算子でリストの中に指定した要素が含まれているかを判定する．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

print('Osaka' in L_university)  # True
print('Kanazawa' in L_university)  # False
```

    True
    False


countメソッドでリストに指定した要素が何個含まれているかを取得する．


```python
L_fibo = [0,1,1,2,3,5,8,13]

print(L_fibo.count(1))
```

    2


indexメソッドで指定した要素がリストの何番目にあるかを取得できる．


```python
L_fibo = [0,1,1,2,3,5,8,13]

print(L_fibo.index(5))
print(L_fibo.index(1))
```

    5
    1


sortメソッドでリストの数値を小さい順に並び替えることができる．


```python
L_fibo = [0,1,2,13,8,1,5,3]

L_fibo.sort()  # reverse=Trueを指定すると大きい順に並び替えられる．

print(L_fibo)
```

    [0, 1, 1, 2, 3, 5, 8, 13]


reverseメソッドでリストの並び順を逆にすることができる．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

L_university.reverse()

print(L_university)
```

    ['Kyusyu', 'Osaka', 'Kyoto', 'Nagoya', 'Tokyo', 'Tohoku', 'Hokkaido']


max関数/min関数でリスト内の要素の最大値/最小値を取得できる．


```python
L_fibo = [0,1,1,2,3,5,8,13]

print(max(L_fibo))
print(min(L_fibo))
```

    13
    0



```python
L_fibo = [0,1,1,2,3,5,8,13]

# indexメソッドとの組み合わせ
print(L_fibo.index(max(L_fibo)))
print(L_fibo.index(min(L_fibo)))
```

    7
    0


組み込み関数のlen関数でリスト内の要素の個数を調べることができる．


```python
L_fibo = [0,1,1,2,3,5,8,13]

print(len(L_fibo))
```

    8


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
