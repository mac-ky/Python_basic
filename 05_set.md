# set型(集合)
ある条件を満たす集まりのことで，リストやタプルと異なり，要素に順番がなく，重複にも意味がない．そのため，重複した要素を削除したいときなどに利用する．

## 集合の作り方
波括弧とコンマで記述する．


```python
Se_int = {-2, 3, 6, 7, 3, 3, 2, 6}

print(Se_int)  # 重複，順番がないので，{2, 3, 6, 7, -2}となる．

print(type(Se_int))
```

    {2, 3, 6, 7, -2}
    <class 'set'>


集合の要素に更新や削除ができる，リストや辞書を含むことはできない．


```python
Se_int = {-2, 3, [6, 7, 3], 3, 2, 6}

print(Se_int)  # これはエラーになる

print(type(Se_int))
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[25], line 1
    ----> 1 Se_int = {-2, 3, [6, 7, 3], 3, 2, 6}
          3 print(Se_int)  # これはエラーになる
          5 print(type(Se_int))


    TypeError: unhashable type: 'list'


set関数で作成することもできる．


```python
L_int = [-2, 3, 6, 7, 3, 3, 2, 6] 
print(type(L_int))  # リストを用意する．

Se_int = set(L_int)

print(Se_int)

print(type(Se_int))
```

    <class 'list'>
    {2, 3, 6, 7, -2}
    <class 'set'>


空集合を作成するときは辞書型と認識されないように，set関数を使う．


```python
Se_empty = set()
D_empty = {}

print(type(Se_empty))  # これは集合
print(type(D_empty))  # これは辞書
```

    <class 'set'>
    <class 'dict'>


## 集合のメソッド・関数・演算子

addメソッドで集合に要素を追加することができる．


```python
Se_int = {-2, 3, 6, 7, 3, 3, 2, 6}

Se_int.add(1)

print(Se_int)
```

    {1, 2, 3, 6, 7, -2}


removeメソッドで集合から要素を削除することができる．


```python
Se_int = {-2, 3, 6, 7, 3, 3, 2, 6}

Se_int.remove(3)

print(Se_int)
```

    {2, 6, 7, -2}


clearメソッドで集合から全ての要素を削除できる．


```python
Se_int = {-2, 3, 6, 7, 3, 3, 2, 6}

Se_int.clear()

print(Se_int)
```

    set()


## 要素の追加や削除ができない集合
frozenset関数を利用することで作成できる．


```python
L_int = [-2, 3, 6, 7, 3, 3, 2, 6] 
print(type(L_int))  # リストを用意する．

Se_int_f = frozenset(L_int)

print(Se_int_f)

print(type(Se_int_f))
```

    <class 'list'>
    frozenset({2, 3, 6, 7, -2})
    <class 'frozenset'>



```python
L_int = [-2, 3, 6, 7, 3, 3, 2, 6] 
print(type(L_int))  # リストを用意する．

Se_int_f = frozenset(L_int)

Se_int_f.add(1)  # 要素の追加や削除ができないので，これはエラーになる

print(Se_int_f)
```

    <class 'list'>



    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[56], line 6
          2 print(type(L_int))  # リストを用意する．
          4 Se_int_f = frozenset(L_int)
    ----> 6 Se_int_f.add(1)  # 要素の追加や削除ができないので，これはエラーになる
          8 print(Se_int_f)


    AttributeError: 'frozenset' object has no attribute 'add'


## 集合の演算
 - 和集合：集合の少なくともどちらか1つに含まれる要素の集合
 - 積集合：2つの集合のどちらにも含まれる要素の集合
 - 差集合：2つの集合のうち，集合Aには含まれ，集合Bには含まれない要素の集合
 - 対称差集合：2つの集合のうち，どちらかにだけ含まれる要素の集合

バーティカルライン(|)やunionメソッドを使用すると，和集合を作成できる


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {4, 5, 6}

# バーティカルラインで作成
Se_int_uni = Se_int_1 | Se_int_2
print(Se_int_uni)

# unionメソッドで作成
Se_int_uni = Se_int_1.union(Se_int_2)
print(Se_int_uni)
```

    {3, 4, 5, 6}
    {3, 4, 5, 6}


アンパサンド(&)やintersectionメソッドを使用すると積集合を作成できる．


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {4, 5, 6}
Se_int_3 = {5, 6, 7}

# アンパサンドで作成
Se_int_int = Se_int_1 & Se_int_2 & Se_int_3
print(Se_int_int)

# intersectionメソッドで作成
Se_int_int = Se_int_1.intersection(Se_int_2, Se_int_3)
print(Se_int_int)
```

    {5}
    {5}


マイナス(-)やdifferenceメソッドを使用すると，差集合を作成できる．


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {4, 5, 6}

# マイナスで作成
Se_int_dif = Se_int_1 - Se_int_2
print(Se_int_dif)

# differenceメソッドで作成
Se_int_dif = Se_int_1.difference(Se_int_2)
print(Se_int_dif)
```

    {3}
    {3}


ハット(^)やsymmetric_differenceメソッドを使用すると，対称差集合を作成できる．


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {4, 5, 6}

# ハットで作成
Se_int_sym = Se_int_1 ^ Se_int_2
print(Se_int_sym)

# differenceメソッドで作成
Se_int_sym = Se_int_1.symmetric_difference(Se_int_2)
print(Se_int_sym)
```

    {3, 6}
    {3, 6}


## 集合の関係
<=やissubsetメソッドを使用すると，部分集合かどうかを判定できる．


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {3, 4, 5, 6}

# <=で判定
print(Se_int_1 <= Se_int_2)

# issubsetメソッドで判定
print(Se_int_1.issubset(Se_int_2))

```

    True
    True


==で集合が等しいかどうかを判定できる．


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {3, 4, 5, 6, 2}
Se_int_3 = {5, 3, 4}

print(Se_int_1 == Se_int_2)  # False
print(Se_int_1 == Se_int_3)  # True
```

    False
    True


<で真部分集合(部分集合でかつ，等しい集合ではない)かどうか判定できる．


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {3, 4, 5, 6, 2}
Se_int_3 = {5, 3, 4}

print(Se_int_1 < Se_int_2)  # True
print(Se_int_1 < Se_int_3)  # False
```

    True
    False


isdisjointメソッドで2つの集合が互いに素(要素が1つも一致しない)かどうか判定できる．


```python
Se_int_1 = {3, 4, 5}
Se_int_2 = {4, 5, 6}
Se_int_3 = {7, 8, 9}

print(Se_int_1.isdisjoint(Se_int_2))  # False
print(Se_int_1.isdisjoint(Se_int_3))  # True
```

    False
    True


## 要素の存在確認
in演算子を用いて，ある要素が集合に含まれていいるか確認できる．


```python
Se_int = {-2, 3, 6, 7, 3, 3, 2, 6}

print(7 in Se_int)  # True
print(1 in Se_int)  # False
```

    True
    False


for文で集合の要素を取得することができる．


```python
Se_int = {-2, 3, 6, 7, 3, 3, 2, 6}

for i in Se_int:
    print(i)
```

    2
    3
    6
    7
    -2


listに変換してもOK


```python
Se_int = {-2, 3, 6, 7, 3, 3, 2, 6}
L_int = list(Se_int)

print(L_int[1])
```

    3


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
