# 宣言関係
```python
 Array = [] # 配列の宣言
 Dict  = {} # ディクショナリの宣言
```


# rstrip()
#### 改行文字(¥n)を取り除く
 ```python
 LINE = "Hello¥n"
 LINE = LINE.rstrip()
 
 # 結果
 LINE: "hello"
 ```
 
 # append()
 #### 配列の一番後ろに要素を追加
 ```python
 fac1 = "hello"
 fac2 = "world"
 LINE = []
 LINE.append(fac1)
 LINE.append(fac2)
 
 # 結果
 LINE: ['hello", 'world']
 ```
 
 # 配列を，指定した要素でソート
 ```python
 from operator import itemgetter #sort by any factor
 
 LINE = [[PlayStation4, 40000, game],
         [Switch, 30000, game],
         [Xbox, 50000, game]]
         
 # 2番目の要素でソート
 LINE.sort(key=itemgetter(1))
 
 # 結果
 LINE = [[Xbox, 50000, game],
         [Playstation4, 40000, game],
         [Switch, 30000, game]]
 ```
 
 
 # split(',',n)
 #### , で区切る（最大n個まで）
 ```python
 LINE = "a , b , c , d , e"
 Array = LINE.split(',')

 #結果
 Array[0]= 'a'
 Array[1]= 'b'
 Array[2]= 'c'
 Array[3]= 'd'
 Array[4]= 'e'
 ```


# replace('m','n')
#### mをnに変える
```python
LINE = "bython"
LINE = LINE.replace('b','p')

#結果
LINE: python
```

# for文
#### 変数iが1 ~ 65 の間繰り返す
#### （つまり６５回繰り返す）
```python
for i in range(1,66):
```

# ファイルの読み込み・書き込み
```python
import csv

a = open('read.csv','r') # 読み込み専用
b = open('write,csv', 'w') # 書き込み専用

for line in a: # read.csvを，上から一行づづ読み込む

b.write("hello¥n") # write.csvに hello を書き込む．

a.close() #　閉じる
b.close()
```

# len()
#### 配列の要素数を返す
```python
LINE = [1, 2, 3, 4, 5]
N = len(LINE)

# 結果
N = 5
```


# 配列の検索
####  配列を検索し，該当したインデックスをかえす
```python
import math
text = ['5', '28', '11', '12', '28', '28']
indexes = [i for i, x in enumerate(text) if x == '28']

# 結果
indexes = [1, 4, 5]
```


# ディクショナリ
