Title: Shell - 数值计算 笔记
Date: 2018-12-19 11:31
Category: notes

## bc 基础用法

```shell
echo "1+2" | bc
```

3

```shell
echo "scale=5;1/2" | bc
```

.50000

## 求max值 

```shell
echo $(( 2>1?2:1 ))
```

2

```shell
max=`python -c 'print max(1,2)'`
echo $max
```

2