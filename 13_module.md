# モジュール・パッケージ・ライブラリ

## モジュール・パッケージ・ライブラリの違い
- モジュール：関数やクラスをまとめたもので，Pythonファイル(.py)
- パッケージ：複数のモジュールをまとめたフォルダ
- ライブラリ：関数やクラス，モジュール，パッケージなど他のプログラムから呼び出されるものの総称．

## モジュールとパッケージの作成
自作モジュールやパッケージを作成する際は，同一ディレクトリにPythonファイルを作成する．\
以下は一例でarea.pyがモジュール，calculationがパッケージ：\
├──13\_module.ipynb \
├──circle.py \
├──calculation \
&emsp;&emsp;&emsp;├── \_\_init\_\_.py \
&emsp;&emsp;&emsp;├── exponential.py \


### モジュールの作成(一例)
同じディレクトリに次のようなPythonファイルを作成する．\
circle.pyの中身：
```python
pi = 3.14
radius = 2

def area(pi, radius):
    return pi * radius * radius

def length(pi, radius):
    return 2 * radius * pi
```

### パッケージの作成(一例)
同じディレクトリにcalculationというフォルダを作成し，その下に次のファイルを作成する．\
- \_\_init\_\_.pyには何も書かない：このファイルがあることで，calculationがパッケージとして認識される
- exponential.pyの中身：
```python
a = 2
x = 10

def exponential(a, x):
    return a ** x
```

## モジュールとパッケージの使用方法

import文でモジュールやパッケージを読み込み使用することができる．
```python
import モジュール名

from パッケージ名 import モジュール名
```


```python
import circle  # モジュールの読み込み

from calculation import exponential  # パッケージの中のモジュールの読み込み
```

定義した変数や関数を呼び出すことができる．
```python
モジュール名.オブジェクト名
```


```python
import circle  # モジュールの読み込み

r = circle.radius  # circleモジュールで定義した変数を使用する．

print(r)
```

    2



```python
from calculation import exponential  # パッケージの中のモジュールの読み込み

result = exponential.exponential(3, 4)  # exponentialモジュールで定義した関数を使用する

print(result)
```

    81


import文でオブジェクトを読み込むこともできる．
```python
from モジュール名 import オブジェクト名
from パッケージ名.モジュール名 import オブジェクト名
```


```python
from circle import radius, area  # circleモジュールの中のオブジェクトの読み込み

print(radius)
print(area(3.14, 2))
```

    2
    12.56



```python
from calculation.exponential import a, exponential  # calculationパッケージの中のexponentialモジュールの中のオブジェクトの読み込み

print(a)
print(exponential(3,4))
```

    2
    81


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．


```python

```
