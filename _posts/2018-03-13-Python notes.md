---
title: Python Notes
categories: python 
---

## command line

to programming through computer's directories

**cd** current directory 

**cd namex** change current dir into namex  // use tab to autoselect ~

**cd ..** jump back up

**cd cls** clean the screen

**dir** listing the things in current directory

我现在已经把anaconda加入system path了(just for my convenient)，可以直接在cmd跑的语句有：

**python** 进入python interactive mode，>>>为标志。**Ctrl+Z** 退出改mode

**conda xxx** 比如conda list

**jupyter notebook** 直接打开笔记本



---------------------------------

**Values** belong to different **types**:  like integer and string 

A **variable** is a name that refers to a value; legal name ; reserved keywords

A **statement** is a unit contains a sequence of code that the Python interpreter can execute.

**Operator** +,-,\*,/,  \** . The last one is exponentiation. The values the operator is applied to are called **operands**; order of operations- rule of precedence; // and % modulus operator ; + concatenation and * multiply for string. 

**# for commments**



**Boolean expressions** -> returns **True** or **False** (which belongs to special class bool )

**logical operators** : and ; or; not 

```python
if x<y :
    print('x is less than y')
elif x>y :
    print('x is greater than y')
else :
    print('x and y are equal')
```

**try/except **  if an exception occurs in the try block, it will jumps into except block.

```python
inp = input('Enter a number')
try: 
    number = float(inp)
    print(number)
except:
    print('Please enter a number')
    
```

 **def **  function ( parameter name ):    接下一行，用indent确定范围。实际使用function(x - different arguments) , x 是argument. The arguments are assigned to variables called parameters.

```python
def addtow(a,b):
    added=a+b
    return added
```

**Iteration**  *Repeating  identical or similar tasks without making errors is something that computers do well and people do poorly.*  

```python
while True:                     # while ..
    line = input('>')
    if line[0] == '#':
        continue                # continue: jump to next iteration
    if line == 'done':
        break                   # break : jump out of the whole loop
    print(line)
print('Done')
```

**for ...  in ....  : ** go through the list

```python
friends = ['Avery', 'Bella','Yang']  
for name in friends:                   # here name is sth defined by you,没出现过也可以
    print('Happy Valentines Day:',name)
print('Done.')
```



#### string : 'value'  

 a sequence of characters ;

x='banana'     x [ 0 ]= b    ;   [ len(x)-1] or  \[-1] is the last character

string slices : x [ 0 : 2 ]   including the first but excluding the last. 

​                        x [ 2 : ]  == x [ 2 : len(x) ]  == 'nana'

strings are immutable: you can't use x[a] to change  a existing string

... **in** ... / 'a' in 'banana'  / a boolean operator that takes two strings and returns to Ture of False.

**string1 > string2 ** comparison rule: in alphabetical order/ uppercase comes first

**string method $\neq$ function**   method syntax: stringname.method()  / x.upper()  全部转换成大写

```python
x='Xiaofeng He'
type(x)
dir(x)                        # dir: lists the methods avaiable for an object
help(str.isdigit)             # 查看isdigit这个作用在str上的method功能
x.lower().startwith('x')      # 先全部转换为小写，然后判断第一个字母是否为x，returns to True
```





#### Files 

open files

```python
fhand = open('file.txt')      # fhand is the file handle
n = 0

# type in the name. Don't need to chage the code everytime
fname = input('Enter the file name:')           
try:
    fhand = open(fname)
except:
    print('File cannot be opened:',fname)
```

handle files using for

```python
 # txt file = sequence of lines. seperate by \n character  
for line in fhand:           
    n = n + 1 
print('line count:',n)        # count the total lines in a file

for l in fhand:
    l = l.rstrip()            # rstrip - remove whitespace from the right side of a string
    if l.startwith('From:'):
        print(l)
```

writing files - 'w'

```python
fout = open('file.txt','w')      # 注意！如果同名文件存在，会直接变成一个空白新文档
                                 # if the file doesn't exist, a new one is created
fout.write("I love you\n")
fout.write('I love you too\n')
line = "Happy ending\n"
fout.write(line)
```

QA=Quality Assurance - try any attempts possible to test the program 



### List [value]

### Dictionary {key:value, key:value}

```python
word = 'jkalsdfjsdhfa'
d = dict()
for c in word:
    d[c]=d.get(c,0)+1      # use the value in common sense as the diction keys
print d
```

list ( dict1 )  =  dict1.keys ( )   is the list of the keys  in the dictionary dict1

dict1.values ( )   is the list of the values  in the dictionary dict1

dict1.items ( )   = [ (key , value) , (key , value) , (key , value) ]    the tuple



### Tuples (k,v) 

sorted ( )  : if you put a list of tuple [(x1,y1),(x2,y2),(x3,y3)]  ,it will sort by x1,x2,x3 first



## Other

**Different code platform**

1. Text Editor (Atom / Subline text ) compatible for multiple language

2. IDEs - Integrated Developement Enviroment. specifically for python. Working at compnany,larger files( PyCharm / Spyder

3. Notebook - Special-file-format.ipynb . support in-line markdown notes, visualizations, vidooes, and more. ( Jupyter notebook





**小雨的建议**

http://www.cs.cmu.edu/~112/syllabus.html    这个是CMU的python入门课程

http://www.cs.cmu.edu/~112/notes/notes-getting-started.html   这里都可以interactively run, 网站真的是做的太好了



https://leetcode.com/problems/two-sum/description/   leetcode 你做easy难度的就好了，每天做一道leetcode easy
