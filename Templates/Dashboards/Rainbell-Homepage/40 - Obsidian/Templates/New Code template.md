---
项目名称: 
相对路径: 
文件名称: 
代码名称: 
CUID: 20220518002237
所在行: 
语言: python
框架: 
简述: 用于干什么使用呢？注意
tags: code_snippet
---

# New Code template

## 代码名称

我是一个代码的名称

## 代码描述

我是代码内容实现了功能，这里使用 markdown 语法描述

```python
python
```

## 使用注意

使用时候要注意以下几点

## 评论

- 2022-3-27 17 :05: 12 这坨屎一样的代码是我写的吗？
- 2022-3-27 17 :07: 34 天啦，这代码写的简直超神了！
- 2022-3-27 17 :07: 59 TODO 需要改进一下代码结构，关联的几个都需要重构

## 最近代码片段

```dataview
table
		语言,
 		框架,
		简述,
		file.cday AS "创建时间"
from #code_snippet and !"40 - Obsidian/模板"
where date(today) - file.ctime <=dur(7 days)
sort file.mtime desc
limit 10
```

[[00. myCodes|代码管理主页](../../20%20-%20Work%20&%20Study/Codes/00.%20myCodes.md)

---

注：感谢 @咖啡豆 提供模板！
