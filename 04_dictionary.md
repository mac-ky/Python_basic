# 辞書型
複数の要素をもつデータ型で，要素の変更や削除が可能である．keyとvalueの組み合わせでデータが格納されている．

## 辞書の作り方
波括弧とコンマ，コロンで記述する．


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

print(D_age)

print(type(D_age))
```

    {'佐々木': 23, '田中': 54, '中川': 31}
    <class 'dict'>


dict関数で作成することもできる．


```python
d_age =dict(佐々木=23, 田中=54, 中川=31)

print(D_age)

print(type(D_age))
```

    {'佐々木': 23, '田中': 54, '中川': 31}
    <class 'dict'>


keyとvallueをリストでセットにして，dict関数に渡してもよい．


```python
D_age = dict([['佐々木', 23],['田中', 54], ['中川', 31]])

print(D_age)

print(type(D_age))
```

    {'佐々木': 23, '田中': 54, '中川': 31}
    <class 'dict'>


## keyのルール
keyはvalueに対して一意なものである．


```python
# 複数のvalueに対して一つのkeyを指定しようとすると，上書きされてしまう．
D_age = {'佐々木':23, '田中':54, '中川':31, '田中': 46}

print(D_age)

print(type(D_age))
```

    {'佐々木': 23, '田中': 46, '中川': 31}
    <class 'dict'>


## 辞書のメソッド・関数・演算子
keysメソッドとvaluesメソッドでkeyとvalueの一覧を取得できる．


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

print(D_age.keys())
print(D_age.values())

```

    dict_keys(['佐々木', '田中', '中川'])
    dict_values([23, 54, 31])


辞書にはインデックスの考え方がないので，個別のvalueを取得するにはkeyを指定する．


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

print(D_age['田中'])
```

    54


辞書の要素の変更


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

# 要素の変更においてもkeyの指定で行う．
D_age['田中'] = 56

print(D_age)
```

    {'佐々木': 23, '田中': 56, '中川': 31}


辞書の要素の追加


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

D_age['前田'] = 18

print(D_age)
```

    {'佐々木': 23, '田中': 54, '中川': 31, '前田': 18}


updateメソッドで辞書同士での辞書の更新や追加ができる．


```python
D_age1 = {'佐々木':23, '田中':54, '中川':31}
D_age2 = {'前田':18, '鈴木':37}

D_age1.update(D_age2)
print(D_age1)
```

    {'佐々木': 23, '田中': 54, '中川': 31, '前田': 18, '鈴木': 37}


del文で辞書の要素を削除できる．


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

del D_age['田中']

print(D_age)
```

    {'佐々木': 23, '中川': 31}


popメソッドでも削除が可能


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

D_age.pop('田中')

print(D_age)
```

    {'佐々木': 23, '中川': 31}


clearメソッドで辞書の要素を全て削除することができる．


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

D_age.clear()

print(D_age)
```

    {}


in演算子でリストの中に指定した要素が含まれているかを判定する．


```python
D_age = {'佐々木':23, '田中':54, '中川':31}

print('佐々木' in D_age)  # True
print('前田' in D_age)  # False
```

    True
    False


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
