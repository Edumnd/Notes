# Vim编辑器

control+p，编写代码时联想函数参数

Vim 编辑器分两种模式

- 命令模式
- 文本模式
- control + s：冻结vim
- control + q：解冻vim

### Vim 命令

- a 插入光标后
- i 插入光标前
- ESC 返回命令模式
- A 插入行尾
- I 插入行首
- x 删除光标所在字符
- dd 删除一行
- 3dd 删除3行
- D 删除光标到行末
- ^ 光标移至行首
- $ 光标移至行末
- control+d 向下翻半页 (down)
- control+f 向下翻一页 (forward)
- control+u 向上翻半页 (up)
- control+b 向上翻一页 (backward)
- gg 光标到文档头
- G 光标到文档尾
- w 光标前移一个单词
- b 光标后移一个单词
- [n]+ 光标向前移动n行
- [n]- 光标向后移动n行
- [n]G 光标跳转到第n行行首  **重要，用于代码行查找**
- /[str] 查找字符串
  - n 下一个
  - N 上一个
- s/[查找串]/[替换串] ，替换光标所在行的首个匹配串
- s/[查找串]/[替换串]/g，替换光标所在行所有匹配
  - g匹配所有
  - i匹配时忽略大小写
- 2,7 s/[查找串]/[替换串]/ig ，替换2到7行，所有匹配，忽略大小写
- %s/[查找串]/[替换串]/g，替换整个文档
- yy，复制一行
- [n]yy，复制光标所在处n行
- p ，粘贴
- u，撤销操作
- v，v模式可以选中文本
- control+v，竖选v
  - 选中后输入I，就能进入多行插入模式，**可以用于多行注释**
- %!xxd 看16进制
  - -r 参数返回正常文本模式
- new 文件名，横向打开一个新的vim窗口，用于展示新文件
- vnew 文件名，纵向打开一个新的vim窗口
  - 窗口切换用control+ww
- sp 对于同一文件，横向切割成两个窗口
- vsp 对于同一文件，纵向切成两个窗口
- close 关闭窗口
- gg=G 自动对齐



## 批量替换

若有好多个文件，都需要替换其中的某个字段需要用```sed```

```bash
sed -i "s/printf/puts/g" *.c
# 将所有.c文件中的字符串printf 替换成 puts, g参数表示替换整行匹配，
# 类似于vim中的替换
# -i 参数表示执行实际替换，若不加-i参数，则替换只是预演，实际没有执行
```
