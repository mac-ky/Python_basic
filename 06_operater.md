# 演算子
四則演算や大小比較などを行うときの記号のとき

## 算術演算子 
足し算，引き算，掛け算，割り算などを行うためのもの．


```python
a = 15
b = 4

print("足し算：", a + b)
print("引き算：", a - b)
print("掛け算：", a * b)
print("割り算：", a / b)
print("割り算の余り：", a % b)
print("割り算の商：", a // b)
```

    足し算： 19
    引き算： 11
    掛け算： 60
    割り算： 3.75
    割り算の余り： 3
    割り算の商： 3


## 関係演算子
2つの値の関係の真偽を判断させる演算子


```python
a = 15
b = 4

print("aがbより大きいか？：",a > b)  # True
print("bがaより大きいか？：",a < b)  # False
print("aはb以上か？：",a >= b)  # True
print("bはa以上か？：",a <= b)  # False
print("aはbと等しいか？：",a == b)  # False
print("aはbと等しくないか？：",a != b)  # True
```

    aがbより大きいか？： True
    bがaより大きいか？： False
    aはb以上か？： True
    bはa以上か？： False
    aはbと等しいか？： False
    aはbと等しくないか？： True


## 論理演算子
複数の条件を判断させる演算子


```python
a = 15
b = 4

print("aは10以上かつ20以下か？：",a >= 10 and a <= 20)  # True
print("bは10以上かつ20以下か？：",b >= 10 and b <= 20)  # False
print("aは10または，bが20以外か？：",a == 10 or b != 20)  # True
print("aが10より小さいまたは，bが10より大きい？：",a < 10 or b > 10)  # False
```

    aは10以上かつ20以下か？： True
    bは10以上かつ20以下か？： False
    aは10または，bが20以外か？： True
    aが10より小さいまたは，bが10より大きい？： False


## 代入演算子・複合代入演算子
変数を代入するときに使う"="を代入演算子，足し算・引き算などと組み合わせて代入する演算子(e.g.,"+=")のことを複合代入演算子という．


```python
a = 15
b = 4
c = 7

a += 9  # 15 + 9
c += b  # 4 + 7

print(a)
print(c)

```

    24
    11


## is演算子・is not演算子
関係演算子で2つのオブジェクトが同じかどうかを判断する演算子．関係演算子の"=="を使用すると，異なるオブジェクトでも値が同じであれば，Trueが返される．


```python
L_fibo1 = [0,1,1,2,3,5,8,13]
L_fibo2 = [0,1,1,2,3,5,8,13]
L_fibo3 = L_fibo1  # L_fibo3とL_fibo1は同じオブジェクト

print("L_fibo1とL_fibo2が同じ値を持つかどうか：", L_fibo1 == L_fibo2)  # True
print("L_fibo1とL_fibo2が同じオブジェクトかどうか：", L_fibo1 is L_fibo2)  # False
print("L_fibo1とL_fibo3が同じ値を持つかどうか：", L_fibo1 == L_fibo3)  # True
print("L_fibo1とL_fibo3が同じオブジェクトかどうか：", L_fibo1 is L_fibo3)  # True
```

    L_fibo1とL_fibo2が同じ値を持つかどうか： True
    L_fibo1とL_fibo2が同じオブジェクトかどうか： False
    L_fibo1とL_fibo3が同じ値を持つかどうか： True
    L_fibo1とL_fibo3が同じオブジェクトかどうか： True



```python
print("L_fibo1のid：", id(L_fibo1)) 
print("L_fibo2のid：", id(L_fibo2)) 
print("L_fibo3のid：", id(L_fibo3)) 

print("L_fibo1とL_fibo2のidが同じかどうか：", id(L_fibo1) == id(L_fibo2))  # False
print("L_fibo1とL_fibo2のidが同じかどうか：", id(L_fibo1) == id(L_fibo3))  # True

```

    L_fibo1のid： 4676702656
    L_fibo2のid： 4676699072
    L_fibo3のid： 4676702656
    L_fibo1とL_fibo2のidが同じかどうか： False
    L_fibo1とL_fibo2のidが同じかどうか： True


listは変更可能なデータ型であるため，要素の変更を行ってもidは変わらない．


```python
L_fibo = [0,1,1,2,3,5,8,13]

print(L_fibo, id(L_fibo))
L_fibo.append(21)
print(L_fibo, id(L_fibo))
```

    [0, 1, 1, 2, 3, 5, 8, 13] 4676698816
    [0, 1, 1, 2, 3, 5, 8, 13, 21] 4676698816



```python
L_fibo1 = [0,1,1,2,3,5,8,13]
L_fibo2 = [0,1,1,2,3,5,8,13]
L_fibo3 = L_fibo1  # L_fibo3とL_fibo1は同じオブジェクト

print("L_fibo1とL_fibo2が同じオブジェクトかどうか：", L_fibo1 is L_fibo2)  # False
print("L_fibo1とL_fibo2が異なるオブジェクトかどうか：", L_fibo1 is not L_fibo2)  # True
print("L_fibo1とL_fibo3が同じオブジェクトかどうか：", L_fibo1 is L_fibo3)  # True
print("L_fibo1とL_fibo3が異なるオブジェクトかどうか：", L_fibo1 is not L_fibo3)  # False
```

    L_fibo1とL_fibo2が同じオブジェクトかどうか： False
    L_fibo1とL_fibo2が異なるオブジェクトかどうか： True
    L_fibo1とL_fibo3が同じオブジェクトかどうか： True
    L_fibo1とL_fibo3が異なるオブジェクトかどうか： False


## in演算子・not in演算子
複数の要素をもつオブジェクトの中に特定の要素が含まれているかどうかを判定する．


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

print('Osaka' in L_university)  # True
print('Kanazawa' in L_university)  # False
```


```python
L_university = ['Hokkaido','Tohoku','Tokyo','Nagoya', 'Kyoto','Osaka','Kyusyu']

print('Osaka' not in L_university)  # False
print('Kanazawa' not in L_university)  # True
```

    False
    True


## ビット演算子
2進数で表した数値を0と1の羅列とみなして論理演算をする演算子です．

2進数は数値の前に"0b"をつけると，勝手に10進数に変換して表示してくれる．


```python
print(0b111001)  # 57
```

    57


bin関数で10進数を2進数に変換して表示してくれる．


```python
print(bin(57))
```

    0b111001


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
