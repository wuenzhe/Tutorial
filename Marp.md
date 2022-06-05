# Marp

[TOC]

## 文档开头

添加marp

```markdown
---
marp:true
---
```

## 进阶指令

### 指令类型

`theme`更改主题

`paginate`显示页码

`header`编辑页眉

`footer`编辑页脚

`size`调整幻灯片大小

`backgroundColor`背景颜色

`headingDivider`自动分页

### 使用方法

```markdown
<!--
theme: default
paginate: true
-->
```



```markdown
---
marp: ture
theme: default
paginate: true
---
```

## 指令类型

### 全局指令

```markdown
<!-- backgroundColor: aqua -->

This page has aqua background.

---

The second page also has same color.
```

### 局部指令

在指令前添加_，将命令运用于当前页面

```markdown
<!-- _backgroundColor: aqua -->

Add underscore prefix `_` to the name of local directives.

---

The second page would not apply setting of directives.
```

## 标题分隔符

`headingDivider`根据标题进行自动分页

```markdown
<!-- headingDivider: 2 -->

# 1st page

The content of 1st page

## 2nd page

### The content of 2nd page

Hello, world!

# 3rd page

Thanks 
```

## 页码

```markdown
<!-- paginate: true -->

You would be able to see a page number of slide in the lower right.
```

仅在非标题页出现页面

```markdown
# Title slide

This page will not paginate by lack of `paginate` local directive.

---

<!-- paginate: true -->

It will paginate slide from a this page.
```

## 页眉与页脚

```markdown

---

marp: true
header: '华南农业大学'
footer: 吴恩喆

---

# VS Code + Marp : 用 Markdown 制作幻灯片

##### 作者：吴恩喆
##### 邮箱: enzhewu@outlook.com

--- 

### 文章目录

- #### 一、前言
- #### 二、下载与安装
- #### 三、操作教程
- #### 四、讨论
- #### 五、参考资料
- #### 六、相关推文
```

## 主题风格

Marp内设Default、Gaia和uncover三种

```markdown
---
marp: true
---
<!-- theme: Default-->

## <!-- fit --> VS Code + Marp: 用 Markdown 制作幻灯片

### 来源：SCAU
### 作者：吴恩喆
```

`<!-- fit -->`用于调整主题的大小，以自适应页面

## 图片

`![关键词](路径)`，`[keywords]`用于设置图片参数

### 大小设置

```markdown
![width:200px](image.jpg) <!-- Setting width to 200px -->
![height:30cm](image.jpg) <!-- Setting height to 300px -->
![width:200px height:30cm](image.jpg) <!-- Setting both lengths -->
```

## 背景

`![bg](路径)`可将图片设置为背景，`bg`为关键词

`![bg cover](路径)`缩放图像以填充幻灯片，这也是默认图片设置

`![bg contain](路径)`缩放图像以适应幻灯片

`![bg auto](路径)`不缩放图像，并使用原始大小

`![bg 150%](路径)`按照指定百分比缩放

```markdown
![bg](https://fakeimg.pl/800x600/0288d1/fff/?text=A)
![bg](https://fakeimg.pl/800x600/02669d/fff/?text=B)
![bg](https://fakeimg.pl/800x600/67b8e3/fff/?text=C)
```

垂直排列：

```markdown
![bg vertical](https://fakeimg.pl/800x600/0288d1/fff/?text=A)
![bg](https://fakeimg.pl/800x600/02669d/fff/?text=B)
![bg](https://fakeimg.pl/800x600/67b8e3/fff/?text=C)
```

只显示左侧或右侧

```markdown
![bg left](https://fakeimg.pl/800x600/0288d1/fff/?text=A)
```

