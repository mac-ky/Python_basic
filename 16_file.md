# ファイル操作

## ファイルの種類
- テキストファイル：文字コードを使用して文字で出力できるファイル
- バイナリファイル：コンピュータが理解できるように，データを0と1で表したファイル．

## ファイルの作成・書き込み
open関数でファイルの作成や書き込みができる


```python
f = open("hoge.txt", "w")  # ファイル名とモード(ここでは新規作成作成のwriteモード)を引数に与える
f.write("hogehoge")  # テキストをファイルに書き込む
f.close()  # ファイルの作成を完了

```

hoge.txt：
```text
hogehoge
```


```python
# with文と併せて使うと，close()を書く必要がなくなる
with open("hoge.txt", "w") as f:
    f.write("hogehoge new") 

```

hoge.txt：
```text
hogehoge new
```


```python
# '''(トリプルクォート)で改行を含むテキストをそのまま書き込める
convenience = '''\
ローソン
セブンイレブン
ファミリーマート
'''

with open ("store.txt", "w") as f:
    f.write(convenience)
```

hoge.txt：
```text
ローソン
セブンイレブン
ファミリーマート
```


```python
# モードを"a"にするとファイルの末尾にテキストが追加される(appendモード)
with open("store.txt", "a") as f:
    f.write("サークルＫ\n") 

```

hoge.txt：
```text
ローソン
セブンイレブン
ファミリーマート
サークルＫ

```

## ファイルの読み込み
open関数のモードを"r"(readモード)にする


```python
with open("store.txt", "r") as f:
    print(f.read())

```

    ローソン
    セブンイレブン
    ファミリーマート
    サークルＫ
    



```python
# readlineメソッドではⅠ行ずつ読み込まれるので，任意の行数まで読み込みたいときにはreadlineメソッドを使う
with open("store.txt", "r") as f:
    for i in range(2):
        print(f.readline(), end="")
```

    ローソン
    セブンイレブン


## ファイルの読み込み・書き込み
open関数のモードを"w+", "a+", "r+"にすると，読み込みと書き込みができる．

"r+"モードは基本は読み込みなので，存在しないファイルを指定するとエラーになる．



```python
with open("store.txt", "r+") as f:
    print(f.read())
    f.write("デイリーヤマザキ\n") 

```

    デイリーヤマザキ
    レブン
    ファミリーマート
    サークルＫ
    デイリーヤマザキ


hoge.txt：
```text
ローソン
セブンイレブン
ファミリーマート
サークルＫ
デイリーヤマザキ

```


```python
# readメソッドを使用しない場合テキストの最初から書き込まれる
with open("store.txt", "r+") as f:
    f.write("デイリーヤマザキ\n") 

```

hoge.txt：
```text
デイリーヤマザキ
レブン
ファミリーマート
サークルＫ
デイリーヤマザキ

```


```python
# seekメソッドにテキストの途中の任意の位置から操作できる．
with open("hoge.txt", "r+") as f:
    f.seek(4)
    f.write("fuga")  

```

hoge.txt：
```text
hogefuga new
```

"w+"モードはファイルが存在しない場合は新規作成，存在する場合は上書き


```python
company = '''\
JR北海道
JR東日本
JR東海
JR西日本
JR四国
JR九州
'''

with open("JR.txt", "w+") as f:
    f.write(company)
    print(f.read())  # 書き込んだ時点でファイルの末尾にいるので，それ以降を読み込もうとしても何も表示されない．
```

    


JR.txt：
```text
JR北海道
JR東日本
JR東海
JR西日本
JR四国
JR九州
```


```python
company = '''\
JR北海道
JR東日本
JR東海
JR西日本
JR四国
JR九州
'''

with open("JR.txt", "w+") as f:
    f.write(company)
    f.seek(0)  # 先頭に移動
    print(f.read())
```

    JR北海道
    JR東日本
    JR東海
    JR西日本
    JR四国
    JR九州
    


"w+"モードはファイルの末尾へのテキストの追加と読み込みができる


```python
with open("JR.txt", "a+") as f:
    f.write("JR貨物\n")
    f.seek(0)  # 先頭に移動
    print(f.read())
```

    JR北海道
    JR東日本
    JR東海
    JR西日本
    JR四国
    JR九州
    JR貨物
    


JR.txt：
```text
JR北海道
JR東日本
JR東海
JR西日本
JR四国
JR九州
JR貨物
```

参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
