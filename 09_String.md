# 文字列操作

## 文字列の結合
文字列と文字列の間に"+"を入れると文字列を結合できる．"*"で繰り返すこともできる．


```python
wahaha = "551" + "があるとき〜"

print(wahaha)
```

    551があるとき〜



```python
hayakuchi = "炙りカルビ" * 3

print(hayakuchi)
```

    炙りカルビ炙りカルビ炙りカルビ


joinメソッドを用いた結合もできる．


```python
bunnsetsu = "ネ゙".join(["太郎と","花子は","遊んで","いる．"])

print(bunnsetsu)
```

    太郎とネ゙花子はネ゙遊んでネ゙いる．


上記の方法は文字列同士でしか使えない．


```python
# これはエラーになる

wahaha = 551 + "があるとき〜"

print(wahaha)
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[20], line 3
          1 # これはエラーになる
    ----> 3 wahaha = 551 + "があるとき〜"
          5 print(wahaha)


    TypeError: unsupported operand type(s) for +: 'int' and 'str'


## 文字列の分割
splitメソッドで指定した区切り文字で分割することができる．


```python
x = "お も て な し"
a = x.split()  # デフォルトはスペースで分割

print(a)
```

    ['お', 'も', 'て', 'な', 'し']



```python
x = "お-も-て-な-し"
a = x.split(sep="-")  # 区切り文字にハイフンを指定

print(a)
```

    ['お', 'も', 'て', 'な', 'し']


## 文字列の検索
in演算子を用いて特定の文字が含まれているかを確認することができる．


```python
right_phrase = "オーロラを見られる．"
wrong_phrase = "オーロラを見れる．"

print("ら" in right_phrase)
print("ら" in wrong_phrase)  # ら抜き言葉
```

    True
    False


findメソッドを使用すると，指定した文字のインデックス番号が返ってくる．含まれていない場合は-1が返ってくる．


```python
greeting = "Hello Python!"

P = greeting.find("P")  # スペースも1文字としてカウント
python = greeting.find("python")  # 大文字と小文字は区別する

print(P)
print(python)
```

    6
    -1


## 文字列の置換
replaceメソッドを使用すると，文字列の一部を任意の文字列に置換することができる．


```python
kanntou = "私達は マクドナルドのことを マックと呼びます"
kannsai = kanntou.replace("マック", "マクド")

print(kanntou)
print(kannsai)
```

    私達は マクドナルドのことを マックと呼びます
    私達は マクドナルドのことを マクドと呼びます


## 変数を含む文字列
formatメソッドを使用して，クオーテーションの中でも変数を呼び出せるようにする．


```python
N = 2 ** 10

print("2の10乗は{}です．".format(N))
```

    2の10乗は1024です．



```python
# formatメソッドの引数に計算式を与えることもできる．
a = 2
x = 10

print("{}の{}乗は{}です．".format(a, x, a ** x))
```

    2の10乗は1024です．



```python
# 呼び出す順番を変える方法．
a = 2
x = 10

print("{1}の{0}乗は{2}です．".format(x, a, a ** x))
```

    2の10乗は1024です．



```python
# キーワード引数で呼び出すこともできる
a = 2
x = 10

print("{tei}の{shisuu}乗は{result}です．".format( result=a ** x, shisuu=x, tei=a))
```

    2の10乗は1024です．


コロンの後に書式を指定することもできる．


```python
a = 2
x = 10

print("{}の{}乗は{:.2f}です．".format(a, x, a ** x))
```

    2の10乗は1024.00です．


フォーマット済みメソッドを用いることもできる．(Python3.6以降)


```python
# formatメソッドの引数に計算式を与えることもできる．
a = 2
x = 10

print(f"{a}の{x}乗は{a ** x}です．")
```

    2の10乗は1024です．



```python
# formatメソッドでの書式指定
a = 2
x = 10

print(f"{a}の{x}乗は{a ** x:.2e}です．")
```

    2の10乗は1.02e+03です．


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
