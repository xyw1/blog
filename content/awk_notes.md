Title: awk 笔记
Date: 2018-11-29 14:18
Category: notes

去掉fastq文件中的UMI（前21bp）,再将文件输出到标准输出

- if else 嵌套判断
- match() 函数
- substr() 函数

```shell
        cat $fq | awk '{
                if (match($0,/^@/))
                        {
                                print $0
                        }
                else if ( $0=="+" )
                        {
                                print $0
                        }
                else
                        {
                                print substr($0,22)
                        }
                }' | less

```

