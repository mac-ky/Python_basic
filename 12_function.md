# 関数
様々な処理をまとめて一つにしたもの．
- 同じコードを2回書かずに済む
- 1行で使いまわしができる
- 他の人も使うことができる

## 関数の種類
- 自作する関数
- Pythonですでに用意されている組み込み関数(e.g., print関数)

## 関数の定義，引数，戻り値
- "def"を用いて関数を定義する
- defの後に関数名を記述する
- その後ろに関数に渡したい引数を記述する(省略可能)
- "return"で返したい処理を記述することができる

## 引数なしの関数


```python
def say_hello():  # 引数を省略
    print("Hello Python!")  # "Hello Python!"と表示させる関数

say_hello()
```

    Hello Python!


## 引数ありの関数


```python
def greeting(greeting_word):  # greeting_wordという引数を指定
    print(greeting_word)  # 引数として指定した文字を表示させる関数

greeting("こんにちは")
```

    こんにちは


## 複数の引数がある関数


```python
# 指数関数
def exponential(a, x):  # 2つの引数を指定
    print(a ** x)

exponential(2, 10)
```

    1024


## 戻り値がある関数
関数の結果をreturnで返すことができる．


```python
# 指数関数
def exponential(a, x):  # 2つの引数を指定
    return (a ** x)

exponential(2, 10)  
```




    1024



returnで返した戻り値を他の関数でも使用することができる．


```python
# 指数関数
def exponential(a, x):  # 2つの引数を指定
    return (a ** x)

result = exponential(2, 10)  

def print_result(result):
    print(f"計算結果は{result}です．")

print_result(result)
```

    計算結果は1024です．


## デフォルト引数
引数にあらかじめデフォルトの値を渡しておくことができる．


```python
# デフォルトの引数を与えていないので，引数を渡し忘れるとエラーになる．
def exponential(a, x):  
    return (a ** x)

exponential()  
```


    ---------------------------------------------------------------------------

    TypeError                                 Traceback (most recent call last)

    Cell In[62], line 5
          2 def exponential(a, x):  
          3     return (a ** x)
    ----> 5 exponential()


    TypeError: exponential() missing 2 required positional arguments: 'a' and 'x'



```python
# デフォルト引数を与えているので，引数を渡し忘れてもエラーは起きない
def exponential(a=2, x=10): 
    return (a ** x)

exponential()  
```




    1024




```python
# デフォルト引数を与えていているときに，デフォルトと異なる値を渡すと上書きされる
def exponential(a=2, x=10): 
    return (a ** x)

exponential(3, 4)  
```




    81



注意点1：デフォルト値の有無が混在する場合


```python
# デフォルト値の有無が混在する場合は，デフォルト値を渡さない引数を優先的に記述する．
# これはエラーになる
def exponential(a=2, x): 
    return (a ** x)

exponential(3, 4)  
```


      Cell In[74], line 3
        def exponential(a=2, x):
                             ^
    SyntaxError: non-default argument follows default argument




```python
# デフォルト値の有無が混在する場合は，デフォルト値を渡さない引数を優先的に記述する．
def exponential(x, a=2): 
    return (a ** x)

exponential(4,)  
```




    16



注意点2：順次進行の落とし穴


```python
a_default = 2
x_default = 10

def exponential(a=a_default, x=x_default): 
    return (a ** x)

# ここでデフォルト値を指定し直しても，関数を定義した後なので，デフォルト値は上書きされない．
a_default = 3
x_default = 4

exponential()  
```




    1024




```python
def show_list(L=[]):  # 引数にリストL(はじめは空)を指定
    L.append(1)  # リストに要素1を追加
    print(L, id(L))

show_list()  # 空のリストに要素1が追加されて返ってくる
show_list()  # 要素1が入ったリストがデフォルト引数になる
show_list()  # 要素[1,1]が入ったリストがデフォルト引数になる
```

    [1] 4741305152
    [1, 1] 4741305152
    [1, 1, 1] 4741305152


## キーワード引数
名前で値を渡す引数を指定することができる．


```python
# 位置引数(順番で引数を指定する)の場合
def exponential(a, x):  
    return (a ** x)

exponential(10, 2)  # 2の10乗を計算してほしいのに渡す引数の順番を間違えてしまった  
```




    100




```python
# キーワード引数(名前で引数を指定する)の場合
def exponential(a, x):  
    return (a ** x)

exponential(x=10, a=2)  # 順番ではなく名前で指定するので，ミスの心配がない
```




    1024



注意点：キーワード引数と位置引数が混在する場合


```python
# 位置引数を先に書かないとエラーになる
# これはエラーになる
def exponential(a, x):  
    return (a ** x)

exponential(x=10, 2) 
```


      Cell In[96], line 6
        exponential(x=10, 2)
                           ^
    SyntaxError: positional argument follows keyword argument




```python
# 位置引数を先に書かないとエラーになる
# これはエラーになる
def exponential(a, x):  
    return (a ** x)

exponential(2, x=10) 
```




    1024



## 可変長位置引数
引数の前にアスタリスクを書くと可変長位置引数を指定できる．可変長位置引数は"args"とすることが多い．組み込み関数のprint関数やmax関数で用いられている．


```python
def arutoki(dinner, *args):
    print(dinner)
    print(args)  # Tupleとして渡される

arutoki("今日のご飯は", 5, 5, 1)
```

    今日のご飯は
    (5, 5, 1)



```python
def arutoki(dinner, *args):
    print(dinner)
    print(*args)  # Tupleが展開されて表示される

arutoki("今日のご飯は", 5, 5, 1)
```

    今日のご飯は
    5 5 1



```python
def arutoki(dinner, *args):
    print(dinner)
    for i in args:  # 引数を一つずつ取り出すことも可能
        print(i)
    
arutoki("今日のご飯は", 5, 5, 1)
```

    今日のご飯は
    5
    5
    1


## 可変長キーワード引数
複数のキーワード指定された引数を辞書として受け取れる．可変長キーワード引数は"kwargs"とすることが多い．組み込み関数のdict関数などで用いられている．


```python
def exponential(**kwargs):
    print(kwargs)

exponential(a=2, x=10, result=2**10)
```

    {'a': 2, 'x': 10, 'result': 1024}



```python
def exponential(**kwargs):
    print(kwargs)

D = {'a': 2, 'x': 10, 'result': 1024}  # このままDを関数exponentialの引数として渡すと，Dが位置引数になるのでエラーが起こる

exponential(**D)  # Dを辞書として展開できるようにして渡す
```

    {'a': 2, 'x': 10, 'result': 1024}


## 関数内関数
関数の中で似たような処理を繰り返したいときに使う．


```python
def outer_func(a, b):
    def inner_func(c, d):
        return c - d

    x = inner_func(2,1)
    y = inner_func(a, b)
    print(x)
    print(y)

outer_func(5,8)
```

    1
    -3


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．
