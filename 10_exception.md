# 例外処理
プログラムでエラーが発生してもその先の処理を実行させるためのもの．

## Pythonのエラー
- 構文エラー：コードが文法的に間違っている
- 例外エラー：文法的に正しかったとしても実行するうえで不具合が生じる．\
例外が発生したときにどのように対処するかを書く処理が例外処理．例外処理が書かれていてエラーが発生すると，プログラムは停止してしまう．


```python
# 構文エラーの例
wahaha = 551 + "があるとき〜"

print(wahaha)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[20], line 2
          1 # 構文エラーの例
    ----> 2 wahaha = 551 + "があるとき〜"
          4 print(wahaha)


    TypeError: unsupported operand type(s) for +: 'int' and 'str'



```python
# 例外エラーの例

x = 5
y = 0

print("計算開始")
print(x / y)
print("計算終了")
```

    計算開始



    ---------------------------------------------------------------------------

    ZeroDivisionError                         Traceback (most recent call last)

    Cell In[25], line 7
          4 y = 0
          6 print("計算開始")
    ----> 7 print(x / y)
          8 print("計算終了")


    ZeroDivisionError: division by zero


## try ~ except
エラーが発生したときの処理を指定しておくことができる．


```python
# エラーが発生する場合の処理
x = 5
y = 0

print("計算開始")
try:
    print(x / y)
except:
    print("0では割れましぇん")

```

    計算開始
    0では割れましぇん



```python
# エラーが発生しない場合の処理
x = 5
y = 1

print("計算開始")
try:
    print(x / y)
except:
    print("0では割れましぇん")

```

    計算開始
    5.0


## try ~ except ~ else
エラーが発生しなかった場合の処理をelseの後ろに書いておく．


```python
# エラーが発生する場合の処理
x = 5
y = 0

print("計算開始")
try:
    print(x / y)
except:
    print("0では割れましぇん")
else:
    print("計算できたヨ!")
```

    計算開始
    0では割れましぇん



```python
# エラーが発生しない場合の処理
x = 5
y = 1

print("計算開始")
try:
    print(x / y)
except:
    print("0では割れましぇん")
else:
    print("計算できたヨ!")
```

    計算開始
    5.0
    計算できたヨ!


## try ~ except ~ else ~ finally
エラー発生の有無に関わらず実行したい処理をfinallyの後ろに書いておく．


```python
# エラーが発生する場合の処理
x = 5
y = 0

print("計算開始")
try:
    print(x / y)
except:
    print("0では割れましぇん")
else:
    print("計算できたヨ!")
finally:
    print("計算終了")
```

    計算開始
    0では割れましぇん
    計算終了



```python
# エラーが発生しない場合の処理
x = 5
y = 1

print("計算開始")
try:
    print(x / y)
except:
    print("0では割れましぇん")
else:
    print("計算できたヨ!")
finally:
    print("計算終了")
```

    計算開始
    5.0
    計算できたヨ!
    計算終了


## 例外処理の場合分け
発生するエラーの種類によって処理を変えることができる．


```python
# 0で割ったことによって生じるエラー
x = 5
y = 0

print("計算開始")
try:
    print(x / y)
except ZeroDivisionError:
    print("0では割れましぇん")
except TypeError:
    print("データ型がアカンねやわ〜")

```

    計算開始
    0では割れましぇん



```python
# 異なるデータ型を用いたことにより生じるエラー
x = 5
y = "0"

print("計算開始")
try:
    print(x / y)
except ZeroDivisionError:
    print("0では割れましぇん")
except TypeError:
    print("データ型がアカンねやわ〜")

```

    計算開始
    データ型がアカンねやわ〜


## エラー内容の出力
エラー内容を受け取ることもできる．


```python
x = 5
y = 0

print("計算開始")
try:
    print(x / y)
except Exception as e:
    print(e)
finally :
    print("計算終了")

```

    計算開始
    division by zero
    計算終了



```python
x = 5
y = "0"

print("計算開始")
try:
    print(x / y)
except Exception as e:
    print(e)
finally :
    print("計算終了")

```

    計算開始
    unsupported operand type(s) for /: 'int' and 'str'
    計算終了


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
