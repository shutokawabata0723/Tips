# インタプリタで実行
#### 開始
```
Python
```
#### 終了
```
quit()
```


# モジュール
#### とりあえずモジュールの上につけとく
```python
#coding:utf-8
```

#### デフォルトで常に欲しい
```python
import csv
import sys
import codecs
import math
import random
```
#### 用途次第
```python
from urlparse import urlparse       #URL --> Domain
from time import sleep              #To sleep
import requests                     #request HTML from URL
from operator import itemgetter     #sort by factor
import matplotlib.pyplot as plt     #Graph 
import numpy as np                  #Graph
```
# モジュールのインストール方法
```
pip install [モジュール名]
または
sudo pip install [モジュール名]
```
#### sudo がどうしても使えないとき
```
pip install [モジュール名] --user
````

# 宣言
```python
 Array = [] # 配列の宣言
 Dict  = {} # ディクショナリの宣言
 Set   = set()
```

# 文字化け
```python
 a = open('in.csv','r') #UTF-8の文字列
 for i in a:
   text = i
   text = text.encode('utf-8')
   print text
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
 LINE: ['hello', 'world']
 ```
 
 # del
 #### 指定したリストの要素を削除
 ```python
 list = [0,1,2,3,4]
 del list[2]
 print list
 ```
 # 結果
 ```
[0,1,3,4] 
 ```
 
 
 
 
 
 # ソート
 #### 一番簡単
 ```python
 data = [5, 2, 3, 1, 4]
 data.sort()
 print data
 
 #結果
 [1, 2, 3, 4, 5]
 ```
 
 #### 組み込み関数版
 ```python
 data = [5, 2, 3, 1, 4]
 data = sorted(data)
 print data 
 
 #結果
 [1, 2, 3, 4, 5]
 ```
 
 #### 文字列をsplitし，単語をアルファベット順にソート
 ```python
 data = 'This is a test string from Andrew'
 list = sorted(data.split(), key=str.lower)
 print list
 
 #結果
['a', 'Andrew', 'from', 'is', 'string', 'test', 'This']
 ```
 
 
 #### 配列を，指定したインデックスでソート
 ```python
 from operator import itemgetter #sort by any factor
 
 LINE = [[PlayStation4, 40000, game],
         [Switch, 30000, game],
         [Xbox, 50000, game]]
         
 # 2番目のインデックスでソート
 LINE.sort(key=itemgetter(1))
 
 # 結果
 LINE = [[Xbox, 50000, game],
         [Playstation4, 40000, game],
         [Switch, 30000, game]]
 ```
 
 #### 要素を逆に並び替える
 ```python
wordList = ["F","A","X"]  #文字列のリスト
numberList = [4,6,2]  #数値のリスト

wordList.reverse()
print (wordList)  #出力結果：["X","A","F"]

numberList.reverse()
print (numberList)  #出力結果：[2,6,4]
```


#### 要素を降順に並び替える（昇順にソート->リバース）
```python
wordList = ["F","A","X"]  #文字列のリスト
numberList = [4,6,2]  #数値のリスト

wordList.sort()
wordList.reverse()
print (wordList)  #出力結果：["X","F","A"]

numberList.sort()
numberList.reverse()
print (numberList)  #出力結果：[6,4,2]
```
#### 上と同じ
```python
wordList = ["F","A","X"]  #文字列のリスト
numberList = [4,6,2]  #数値のリスト

wordList.sort(reverse=True)
print (wordList)  #出力結果：["X","F","A"]

numberList.sort(reverse=True)
print (numberList)  #出力結果：[6,4,2]
```
#### 多次元リストのソート
```python
list = [[10,4],[3,6],[4,6],[5,0],[4,9],[2,0]]
#このリストをまず1番目の要素で昇順にして、次に2番目の要素で昇順にしたい

list.sort(key=lambda x:x[0])
print list
list.sort(key=lambda x:x[1])
print list


#結果
[[2,0], [3,6], [4,6], [4,9], [5,0], [10,4]]
[[2,0], [5,0], [10,4], [3,6], [4,6], [4,9]]
```
 
 #### 1番目の要素を昇順にして、1番目の同じ値が同じものは2番目の値で昇順したい場合
```python
list = [[10,4],[3,6],[4,6],[5,0],[4,9],[2,0]]
list.sort(key=lambda x:(x[0],x[1]))
print list

#結果
[[2,0],[3,6],[4,6],[4,9],[5,0],[10,4]]
```
#### 上と同じ
```python
from operator import itemgetter
list = [[10,4],[3,6],[4,6],[5,0],[4,9],[2,0]]
list.sort(key=itemgetter(1,0))
print list

#結果
[[2,0],[3,6],[4,6],[4,9],[5,0],[10,4]]
```
 
 #### 辞書型のソート
 注意: 返り値としてリストが返ってくる
 ```python
dct = { 2: 3, 3: 4, 1: 2, 0: 8, 4: 2 }
dct = sorted(dct.items())
print dct

#結果
[(0, 8), (1, 2), (2, 3), (3, 4), (4, 2)]
```

#### 上と同じ
```python
dct = { 2: 3, 3: 4, 1: 2, 0: 8, 4: 2 }
for k, v in sorted(dct.items()):
    print str(k) + ": " + str(v)

#結果
0: 8
1: 2
2: 3
3: 4
4: 2
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
#### 変数iが1 ~ 65 の間繰り返す（つまり６５回繰り返す）
```python
for i in range(1,66):
```
#### 配列を前から順に読み込み
```python
LINE = [1, 2, 3, 4, 5]
for a in LINE:
 print a

#結果
1
2
3
4
5
```


# ファイルの読み込み・書き込み
```python
import csv

a = open('read.csv','r') # 読み込み専用
b = open('write.csv', 'w') # 書き込み専用

for line in a: # read.csvを，上から一行づづ読み込む

b.write("hello¥n") # write.csvに hello を書き込む．

a.close() #　閉じる
b.close()
```

# len()
#### 配列またはディクショナリの要素数を返す
```python
LINE = [1, 2, 3, 4, 5]
N = len(LINE)

# 結果
N = 5
```
# int()
#### 文字列を数値に直す
```python
n = '5'
N = int(n)

# 結果
N = 5
```
#### float型をint型に直す
```python
n = 5.55
N = int(n)

# 結果
N = 5
```

# abs()
#### 絶対値をかえす
```python
n = -5.55
print abs(n)

#結果
5.55
```

# print
```python
str1 = 'hello'
str2 = 'world'
print str(str1) + str(str2)
```
#### 色付きでprint
```python
PURPLE  = '\033[35m'
RED     = '\033[31m'
CYAN    = '\033[36m'
OKBLUE  = '\033[94m'
OKGREEN = '\033[92m'
WARNING = '\033[93m'
FAIL    = '\033[91m'
ENDC    = '\033[0m'

print OKGREEN + str(str1) + str(str2) + ENDC
```

# 配列の検索
####  配列を検索し，該当したインデックスをかえす
```python
text = ['5', '28', '11', '12', '28', '28']
indexes = [i for i, x in enumerate(text) if x == '28']

# 結果
indexes = [1, 4, 5]
```


# ディクショナリ
```python
dict = {"itou":64, "yamada":75, "endou":82}
print dict["itou"]
print dict["yamada"]
print dict["endou"]

# 結果
64
75
82
```
#### Keyを取得
```python
KEY = dict.keys()
print KEY

#結果
['itou', 'yamada', 'endou']
```
#### Valueを取得
```python
VAL = dict.values()
print VAL

#結果
[64, 75, 82]
```
#### Keyが存在するかどうか
```python
print "yamada" in dict
print "noguchi" in dict

#結果
True
False
```
#### 要素の追加と更新
```python
dict.update({"honda":52, "endou":92})
print dict

#結果
{"itou":64, "yamada":75, "endou":92, "honda":52}
```
#### Valueに複数の値を持たせる場合(SET型)
```python
dict = {}
name = 'shuto'
kokugo = 60
sugaku = 70
eigo   = 90

dict.setdefault(name, set()).add(kokugo)
dict.setdefault(name, set()).add(sugaku)
dict.setdefault(name, set()).add(eigo)

print dict
```
# 結果
```
{'shuto': set([90, 60, 70])}
```

#### Valueに複数の値を持たせる場合(LIST型)
```
python
dictio = {}
name = 'shuto'
kokugo = 60
sugaku = 70
eigo = 90

dictio.setdefault(name, []).append(kokugo)
dictio.setdefault(name, []).append(sugaku)
dictio.setdefault(name, []).append(eigo)

print dictio
```
# 結果
```
{'shuto':[60,70,90]}
```






#### Set型に書き込み
```python
Set = set()
Set = dict[name]

print Set

#結果
set([90, 60, 70])
```
# set(集合)
配列とは違い，順序は考慮しない
```python
Set = set()
name = 'honda'
group = 'game'

Set.add(name)
Set.add(group)

print Set

#結果
(['game','honda'])
```
#### set --> list
```python
list(Set)
print list

#結果
['game','honda']
```

#### list --> set
```python
list = ['honda','game']
Set = set(list)
print Set

#結果
(['game','honda'])
```

# スクレイピング
```python
import requests
URL = 'https://github.com/shutokawabata0723/....'
r = requests.get(URL)
content = r.text
```
# コマンドライン引数の取得
ファイル名:test_argv.py
```python
import sys
 
args = sys.argv
 
print(args)
print('第１引数：' + args[1])
print('第２引数：' + args[2])
print('第３引数：' + args[3])

#実行
test_argv.py python izm com

#結果
['test_argv.py', 'python', 'izm', 'com']
第１引数：python
第２引数：izm
第３引数：com
```
# URL --> domain
```python
from urlparse import urlparse  

url = 'https://github.com/shutokawabata0723/Tips/edit/master/README.md'
Domain = '{uri.scheme}://{uri.netloc}/'.format(uri=urlparse(url))
print Domain

#結果
https://github.com/
```
# 配列のシャッフル
```python
import random

list = range(100)
random.shuffle(list)
print list
```
#### 結果
```python
[70, 5, 87, 90, 54, 71, 25, 1, 60, 85, 3, 61, 28, 77, 24, 8, 44, 91, 22, 93, 64, 21, 9, 46, 34, 16, 27, 38, 95, 82, 13, 19, 42, 53, 98, 51, 37, 43, 65, 18, 92, 72, 14, 89, 59, 7, 99, 30, 50, 31, 80, 26, 2, 6, 39, 11, 55, 79, 73, 84, 81, 45, 69, 48, 62, 32, 41, 76, 83, 35, 56, 74, 52, 49, 57, 58, 36, 67, 97, 96, 47, 40, 78, 68, 17, 15, 75, 10, 66, 20, 94, 33, 86, 63, 23, 0, 12, 4, 88, 29]
```

# 配列の合計
```python
A = [1,2,3,4,5]
B = sum(A)

print B
```
#### 　結果
```
15
```
# 文字化け関係（BeautifulSoupで解消）
例
```python
url = 'http://kenjasyukatsu.com'
import requests
req = requests.get(url)
from bs4 import BeautifulSoup as bs
soup = bs(req.content, 'html.parser')
# タグ，'meta'を含む部分のみ表示してみる
print soup.find_all('meta')
```
# エクセルファイルxlsxの読み込み
```python
coding:utf-8
import xlrd
import codecs
import os
#エクセルファイルを読み込んでリストに
def readXLSX(name):
       book = xlrd.open_workbook(name)
       sheet = book.sheet_by_index(0)
       read_list = []
       for row_index in range(sheet.nrows):
           read_list.append(sheet.row_values(row_index) ) #1行分のリストを追加
       return read_list
result = readXLSX("sample.xlsx")
```
