Title: Shell - String Parsing
Date: 2018-11-27 17:18
Category: notes
# 按分隔符分割
## 方法一

```shell
a='111|222|333'    
OIFS=$IFS; IFS="|"; set -- $a; aa=$1;bb=$2;cc=$3; IFS=$OIFS 
echo $aa $bb $cc 
```
111 222 333
## 方法二
```shell
echo "1,2,3,4,5" | cut -d ',' -f 1,2 3
```
1 2 3
```shell
echo "1,2,3,4,5" | cut -d ',' -f1
```
1
## 方法三
```shell
line="1,2,3,4,5,6"
OLD_IFS=$IFS
IFS=','
arr=($line)
echo ${arr[0]} ${arr[1]} ${arr[2]}
```
1 2 3
```shell
for d in ${arr[@]}
do
	echo $d
done
```
1
2
3
4
5
6
# 按索引分割
```shell
str=123456
echo ${str:1}
```
23456
```shell
echo ${str:0:-1}
```
12345