![](https://tse2-mm.cn.bing.net/th/id/OIP-C.Ti0lzGMvFXvb5XDr5YLLdgHaHC?w=162&h=180&c=7&r=0&o=5&dpr=1.3&pid=1.7)
# Linux课堂笔记

Linux有三剑客

1. grep文本过滤
2. sed擅长取行
3. awk擅长取列
   
awk[选项] '[匹配]{动作}'
```
awk '{print $1}' students.dat
```

$0表示整行

$1、$2等分别表示第一、二个字段，以此类推
```
awk '{print $1,$3}' student.dat
```

-F指定分隔符（默认为空格或tab）
```
awk -F "," '{print $2}' student.dat
```

布尔表达式匹配（语法类似C语言）

正式表达式匹配
```
awk '$2<60 {print $0}' student.dat
```

```
awk '/stu4/ {print $0}' student.dat
```

使用类型C语言的printf
```
awk '{printf("%4s %3d %3d\n", $1, $2, $3)}' student.dat
```

awk也支持从管道读取内容
```
echo "1 2 3 "| awk '{print $2}'
```


# 大作业完成步骤

1. 在linux系统中下载hugo
```
wget https://github.com/gohugoio/hugo/releases/download/v0.80.0/hugo_0.80_Linux-64.bit.deb
```
2. 下载dpkg，用来安装hugo
```
yum intall dpkg 
```
3. 安装hugo
```
sudo dpkg -i hugo_0.80_Linux-64.bit.deb
```
4. 查看hugo是否安装成功
```
hugo version
```
5. 创建博客
```
hugo new site hugo
```
6. 在hugo官网下载自己喜欢的主题
   

7. 将主题克隆到Linux中的hugo（博客名）中
```
git clone https://github.com/adityatelange/hugo-PaperMod themes /PaperMod --depth=1
```
8. 访问主题
```
hugo sever --bind="0.0.0.0"
```
