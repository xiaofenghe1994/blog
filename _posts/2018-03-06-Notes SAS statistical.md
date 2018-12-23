---
title: SAS Notes
categories: SAS
---

***learning to code: top to bottom***

about typora:

code:  inline- directly press `   / or use code block for large paragraph     

intent  `ctrl+[ or ctrl+]`

##System

comment `\*message;` `\*/massage/\*`	两种注释的方法			 		

option 	`OPTIONS LINESIZE=80 NODATE;` 输出行最大长度为80. 今天的日期不出现在输出的顶部

##Data Input

####different ways to get new data: 

-  use viewtable to type in the data/ import wizard.  no code needed.

-  `INPUT name name name name $ name ;` divide each variable name by blank. If  content is not numerical, use $ after the variable name.
  - after input `DATALINES;` function. then type the data in code. end the data with `;`
  - before input `INFILE 'data-path';`in windows. 

- `IMPORT DATAFILE` normal PC files.

  > PROC  IMPORT  DATAFILE= 'data-path' 
  >
  > ​            OUT = data-set   REPLACE;





Temporary data set:  `work.mydata` -shows in log. But just use `mydata` in code. work is the default library.

#### Permanent Data

- Creating. `LIBNAME libref 'drive:\directory'` 创建一个libref数据库，路径为drive:\directory' . 之后再用

  ```sas
  DATA libref.mydata; 
  INFILE 'data-path'; 
  INPUT Y X1 X2 X3; 
  RUN; 
  ```

  就得到了一个在libref里面的永久数据集mydata, 在log里面显示libref.mydata。

-  Reading在库里读取. Just include a statement in your program. `LIBENAME whatevername 'path of permanent data- mydata'` then `whatevername.mydata`will be the same as `libref.mydata`

  ##### Direct referencing直接指代.

   `DATA 'drive:\path\foldername'` ，再INFILE和INPUT。

  直接用地址来读取永久数据，比如输出数据

  ```SAS
  PROC PRINT DATA= 'drive:\path\foldername';
       TITLE 'foldername';
  RUN;
  ```

  ​

##Working with your data

#### Define  variables. types

numeric constant x=10; character constant x = 'ten' ; x=y;  x= x**10-8







##Computational notation

`rannor();` 

`x**y` is $x^y$







##Logical and loop statements

####IF-THEN ; ELSE IF THEN; 

note that not equal is `~=; ^=;`    

AND `&`     OR`|; !`

#### RETAIN x ;  SUM 迭代: x + change  

因为DATA STEP本来就是一个按照row 的LOOP，RETAIN x可以让x保持上一次的值

#### ARRAY 







##HW.

Details in data manipulate

1. two different data table, how to merge then. (Credit card, some fixed data, some addable data)
2. `PROC SORT` 

