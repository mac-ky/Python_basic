# クラス


## クラスの基本的な概念
クラスとはデータと処理をまとめたもの．Pythonではクラス内のデータのことをアトリビュート，処理のことをメソッドという．
- アトリビュート：クラス内で定義された変数．数値などの代入や参照が可能
- メソッド：クラス内で定義された関数．様々な処理をまとめて一つにしたもの．

### メソッド


```python
class Student:  # クラスを定義．クラス名の最初の1文字は大文字にするのが慣習
    
    def avg(self):  # メソッドの定義．関数と違って必ず引数が必要で，selfとするのが慣習
        print((80 + 70) / 2)

```

### インスタンス化
クラスはクラスから作られたインスタンスを変数に代入して使う．\
上記のコードについて，a001の点数が80点と70点であったとする．


```python
class Student:  # クラスを定義．クラス名の最初の1文字は大文字にするのが慣習
    
    def avg(self):  # メソッドの定義．関数と違って必ず引数が必要で，selfとするのが慣習
        print((80 + 70) / 2)

a001 = Student()  # インスタンス化
a001.avg()  # 定義したメソッドて計算
```

    75.0



```python
class Student:  # クラスを定義．クラス名の最初の1文字は大文字にするのが慣習
    
    def avg(self, math, english):  # メソッドの定義．関数と違って必ず引数が必要で，selfとするのが慣習
        print((math + english) / 2)

a001 = Student()  # インスタンス化
a001.avg(80,70)  # 定義したメソッドて計算
```

    75.0


### アトリビュート


```python
class Student:  # クラスを定義
    
    def avg(self, math, english):  # メソッドを定義．
        print((math + english) / 2)

a001 = Student()  # インスタンス化
a001.avg(80,70)  # 定義したメソッドて計算

a001.name = "sato"  # nameというアトリビュートを定義する
print(a001.name)

```

    75.0
    sato



```python
class Student:  # クラスを定義
        
    def avg(self, math, english):  # メソッドの定義．
        print((math + english) / 2)

a001 = Student()  # インスタンス化
a001.avg(80,70)  # 定義したメソッドて計算

a001.name = "sato"  # nameというアトリビュートを定義する
print(a001.name)

print(a001.gender)  # 定義されていないのでエラーになる

```

    75.0
    sato



    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[10], line 12
          9 a001.name = "sato"  # nameというアトリビュートを定義する
         10 print(a001.name)
    ---> 12 print(a001.gender)  # 定義されていないのでエラーになる


    AttributeError: 'Student' object has no attribute 'gender'


アトリビュートはインスタンスごとに存在する．つまり，新しいインスタンスを作るごとにアトリビュートを定義する必要がある．


```python
class Student:  # クラスを定義
    
    def avg(self, math, english):  # メソッドの定義．
        print((math + english) / 2)

a001 = Student()  # インスタンス化
a001.avg(80,70)  # 定義したメソッドて計算

a001.name = "sato"  # nameというアトリビュートを定義する
print(a001.name)

a002 = Student()
print(a002.name)  

```

    75.0
    sato



    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[18], line 13
         10 print(a001.name)
         12 a002 = Student()
    ---> 13 print(a002.name)  


    AttributeError: 'Student' object has no attribute 'name'



```python
class Student:  # クラスを定義
    
    def avg(self, math, english):  # メソッドの定義．
        print((math + english) / 2)

a001 = Student()  # インスタンス化
a001.avg(80,70)  # 定義したメソッドて計算
a001.name = "sato"  # nameというアトリビュートを定義する
print(a001.name)

a002 = Student()
a001.avg(50,65)  # 定義したメソッドて計算
a002.name = "tanaka"
print(a002.name)  # 定義されていないのでエラーになる


```

    75.0
    sato
    57.5
    tanaka


### コンストラクタ(初期化メソッド)
インスタンスごとにアトリビュートを定義するという不便さを解消するもので，インスタンス化するときに自動的に実行されるメソッドなので，アトリビュートを作っておくことに利用できる．


```python
class Student:  # クラスを定義
    
    def __init__(self):  # 初期化メソッドの定義．引数はselfとするのが慣例
        self.name = ""  # アトリビュートを定義
        
    def avg(self, math , english):  # メソッドを定義．
        print((math + english) / 2)

a001 = Student()  # インスタンス化
a001.name = "sato"  # nameというアトリビュートを定義する
print(a001.name)

a002 = Student()
print(a002.name)  # 初期化メソッドで定義したので，エラーにはならない
```

    sato
    



```python
class Student:  # クラスを定義
    
    def __init__(self):  # 初期化メソッドの定義．引数はselfとするのが慣例
        self.name = ""  # アトリビュートを定義
        
    def avg(self, math , english):  # メソッドを定義．
        print((math + english) / 2)

a001 = Student()  # インスタンス化
a001.name = "sato"  # nameというアトリビュートを定義する
print(a001.name)

a002 = Student()
a002.name = "tanaka"
print(a002.name)  # 初期化メソッドで定義したので，エラーにはならない
```

    sato
    tanaka



```python
class Student:  # クラスを定義
    
    def __init__(self, name):  # 初期化メソッドの定義．第2引数にアトリビュート代入用の変数を記述
        self.name = name  # アトリビュートを定義
        
    def avg(self, math , english):  # メソッドを定義．
        print((math + english) / 2)

a001 = Student("sato")  # インスタンス化と同時にアトリビュートを代入する
print(a001.name)

a002 = Student("tanaka")
print(a002.name)  # 初期化メソッドで定義したので，エラーにはならない
```

    sato
    tanaka


## クラスの複雑な概念

## デストラクタ
インスタンスが不要になり，削除されるときに呼び出されるメソッド．


```python
class Student:  # クラスを定義
    
    def __init__(self, name):  # コンストラクタを定義
        self.name = name  # アトリビュートを定義
        
    def __del__(self):  # デストラクタを定義．
        print("Good Bye!")
        
person = Student("sato")  # インスタンス化
print(person.name)

```

    Good Bye!
    sato



```python
# del文でインスタンスを削除し，デストラクタを呼び出す
class Student:  # クラスを定義
    
    def __init__(self, name):  # コンストラクタを定義
        self.name = name  # アトリビュートを定義
        
    def __del__(self):  # デストラクタを定義．
        print("Good Bye!")
        
person = Student("sato")  # インスタンス化
print(person.name)
del person  # インスタンスを削除
print("hoge")
```

    Good Bye!
    sato
    Good Bye!
    hoge



```python
# del文でインスタンスを削除し，デストラクタを呼び出す
class Student:  # クラスを定義
    
    def __init__(self, name):  # コンストラクタを定義
        self.name = name  # アトリビュートを定義
        
    def __del__(self):  # デストラクタを定義．
        print("Good Bye!")
        
person = Student("sato")  # インスタンス化
print(person.name)
del person  # インスタンスを削除
print(person.name)  # 削除しちゃったので使えない
```

    sato
    Good Bye!



    ---------------------------------------------------------------------------

    NameError                                 Traceback (most recent call last)

    Cell In[47], line 13
         11 print(person.name)
         12 del person  # インスタンスを削除
    ---> 13 print(person.name)  # 削除しちゃったので使えない


    NameError: name 'person' is not defined


## クラスの継承
あるクラスをきほんとして そこからさらに別の機能を持つクラスを作ること．
- 親クラス(スーパークラス)：継承元のクラス
- 子クラス(サブクラス)：継承先のクラス


```python
class Student:  # 学生全体に関するクラス
    def math(self, score):
        print(score)

class Grade1:  # 1年生だけに関するクラス
    def math(self, score):
        print(score)

    def english(self, score):
        print(score)

studentA = Student()
studentB = Grade1()
studentA.math(50)
studentB.math(60)
studentB.english(70)
```

    50
    60
    70



```python
class Student:  # 親クラスの定義
    def math(self, score):
        print(score)

class Grade1(Student):  # 子クラスの定義
    def english(self, score):
        print(score)

studentA = Student()
studentB = Grade1()
studentA.math(50)
studentB.math(60)
studentB.english(70)
```

    50
    60
    70



```python
class Student:  # 親クラスの定義
    def math(self, score):
        print(score)

class Grade1(Student):  # 子クラスの定義
    def english(self, score):
        print(score)

studentA = Student()
studentB = Grade1()
studentA.math(50)
studentB.math(60)
studentB.english(70)
studentA.english(40)  # 子クラスで定義したメソッドを親クラスで使うことはできない
```

    50
    60
    70



    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[55], line 14
         12 studentB.math(60)
         13 studentB.english(70)
    ---> 14 studentA.english(40)  # 子クラスで定義したメソッドを親クラスで使うことはできない


    AttributeError: 'Student' object has no attribute 'english'


## メソッドのオーバーライド
親クラスで定義したメソッドを子クラスで改めて定義する．親クラスで定義したメソッドが上書きされる．


```python
class Student:  # 親クラスの定義
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def math(self, score):
        print(score)

class Grade1(Student):  # 子クラスの定義
    def __init__(self, name, age):  # 同じ名前のメソッドを書くことでオーバーライドができるようになる
        self.name = name
        self.age = age
        print("Name :", self.name)
        print(" Age :", self.age)
        
    def english(self, score):
        print(score)

studentA = Student("sato", 15)
studentB = Grade1("tanaka", 12)  # オーバーライドしたメソッドにはprint文があるので，NameとAgeが表示される
```

    Name : tanaka
     Age : 12



```python
class Student:  # 親クラスの定義
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def math(self, score):
        print(score)

class Grade1(Student):  # 子クラスの定義
    def __init__(self, name, age):  # 同じ名前のメソッドを書くことでオーバーライドができるようになる
        print("Name :", self.name)  # 上書きした子クラスのコンストラクタではアトリビュートが定義されていないので，エラーになる．
        print(" Age :", self.age)
        
    def english(self, score):
        print(score)

studentA = Student("sato", 15)
studentB = Grade1("tanaka", 12)  # オーバーライドしたメソッドにはprint文があるので，NameとAgeが表示される
```


    ---------------------------------------------------------------------------

    AttributeError                            Traceback (most recent call last)

    Cell In[67], line 18
         15         print(score)
         17 studentA = Student("sato", 15)
    ---> 18 studentB = Grade1("tanaka", 12)  # オーバーライドしたメソッドにはprint文があるので，NameとAgeが表示される


    Cell In[67], line 11, in Grade1.__init__(self, name, age)
         10 def __init__(self, name, age):  # 同じ名前のメソッドを書くことでオーバーライドができるようになる
    ---> 11     print("Name :", self.name)  # 上書きした子クラスのコンストラクタではアトリビュートが定義されていないので，エラーになる．
         12     print(" Age :", self.age)


    AttributeError: 'Grade1' object has no attribute 'name'


## super関数
親クラスのメソッドを継承しつつ，子クラス独自の機能を追加する


```python
class Student:  # 親クラスの定義
    def __init__(self, name, age):
        self.name = name
        self.age = age
        
    def math(self, score):
        print(score)

class Grade1(Student):  # 子クラスの定義
    def __init__(self, name, age):  # 同じ名前のメソッドを書くことでオーバーライドができるようになる
        super().__init__(name, age)  # 継承したい親クラスのメソッドを書く．引数のselfは不要．
        print("Name :", self.name)  
        print(" Age :", self.age)
        
    def english(self, score):
        print(score)

studentA = Student("sato", 15)
studentB = Grade1("tanaka", 12)  # オーバーライドしたメソッドにはprint文があるので，NameとAgeが表示される
```

    Name : tanaka
     Age : 12


## クラス変数
そのクラスから作成された，全てのインスタンスで共有される変数．他方，インスタンス変数はそのインスタンス特有の変数．


```python
class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age
        
studentA = Student("sato", 15)
print(studentA.job)
print(studentA.name)
print(studentA.age)

studentB = Student("tanaka", 12)  
print(studentB.job)
print(studentB.name)
print(studentB.age)

```

    junior high school student
    sato
    15
    junior high school student
    tanaka
    12



```python
class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    age = 14  # インスタンス変数にもある場合はインスタンス変数が優先される
    
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age
        
studentA = Student("sato", 15)
print(studentA.job)
print(studentA.name)
print(studentA.age)

studentB = Student("tanaka", 12)  
print(studentB.job)
print(studentB.name)
print(studentB.age)

```

    junior high school student
    sato
    15
    junior high school student
    tanaka
    12



```python
class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    age = 14  # インスタンス変数にもある場合はインスタンス変数が優先される
    
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age
        
print(Student.job)  # クラス変数はインスタンスを作成しなくてもアクセスできる
print(Student.age)
```

    junior high school student
    14


## クラスメソッド
インスタンスを作成しなくも呼び出せるメソッド．他方インスタンスメソッドはインスタンスを作成して呼び出す．


```python
class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    age = 14  # インスタンス変数にもある場合はインスタンス変数が優先される

    @classmethod
    def add_age(cls):  # クラスメソッドの引数はclsとするのが慣例
        cls.age += 1
        return cls.age
        
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age
        
print(Student.add_age())  # 14 + 1
```

    15



```python
class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    age = 14  # インスタンス変数にもある場合はインスタンス変数が優先される

    @classmethod
    def add_age(cls):  # クラスメソッドの引数はclsとするのが慣例
        cls.age += 1
        return cls.age
        
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age

studentA = Student("sato", 12)
print(studentA.add_age())  # 14 + 1
```

    15


## スタティックメソッド
クラスメソッドと同様にインスタンスを作成しなくても呼び出せるメソッド．引数を受け取らないのがクラスメソッドやインスタンスメソッドとの違い


```python
class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    age = 14  # インスタンス変数にもある場合はインスタンス変数が優先される

    @classmethod
    def add_age(cls):  # クラスメソッドの引数はclsとするのが慣例
        cls.age += 1
        return cls.age

    @staticmethod
    def greeting():
        print("Hello!")
        
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age

Student.greeting()
```

    Hello!



```python
# スタティックメソッドはクラス内の変数やメソッドに直接アクセスしない

class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    age = 14  # インスタンス変数にもある場合はインスタンス変数が優先される

    @classmethod
    def add_age(cls):  # クラスメソッドの引数はclsとするのが慣例
        cls.age += 1
        return cls.age

    @staticmethod
    def greeting():
        print("Hello!")
        print(f"I am {Student.age}.")
        
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age

Student.greeting()
```

    Hello!
    I am 14.



```python
# スタティックメソッドはクラス内の変数やメソッドに直接アクセスしない
# そのため，クラスの外で定義した普通の関数と同じ機能を持つ

class Student:  # 親クラスの定義
    
    job = "junior high school student"  # クラス変数に代入
    age = 14  # インスタンス変数にもある場合はインスタンス変数が優先される

    @classmethod
    def add_age(cls):  # クラスメソッドの引数はclsとするのが慣例
        cls.age += 1
        return cls.age
        
    def __init__(self, name, age):  # nameとageはインスタンス変数
        self.name = name
        self.age = age

def greeting():
        print("Hello!")
        print(f"I am {Student.age}.")
    
greeting()
```

    Hello!
    I am 14.


参考：以上はキノコードさん([[ブログ](https://kino-code.com/)・[You Tube](https://youtube.com/@kinocode?si=B4f5QLuWVA9U65uI]))のYou Tube動画を見て勉強した内容をまとめたものです．
