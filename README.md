## rstrip()
#### 改行文字(¥n)を取り除く
 ```python
 LINE = "a , b , c , d , e¥n"
 LINE = LINE.rstrip()
 
 LINE = "a , b , c , d , e"
 ```
 ## split(',',n)
 #### ','で区切る（最大n個まで）
 ```python
 LINE = "a , b , c , d , e"
 Array = LINE.split(',')
 
 
 Array[0]: 'a'
 Array[1]: 'b'
 Array[2]: 'c'
 Array[3]: 'd'
 Array[4]: 'e'
 ```
