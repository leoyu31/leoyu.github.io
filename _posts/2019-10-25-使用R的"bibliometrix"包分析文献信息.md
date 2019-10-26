---
layout: post
title: 如何用R分析文献信息?
---

<!--more-->
 
 
有时我们想分析某个领域或话题相关的所有文献, 找出其中影响力最大的文章或作者, 或者其中最早发表的重要文章.利用R的"Bibliometrix"包可以轻松完成这一需求.

首先,在Scopus或Web of Science等摘要索引库中输入搜索条件,选中所有条目,并将文献列表以BibTex格式导出 (**注意: 一定要在导出选项中勾选包含引文信息**).多个BibTex文件可以打包成一个Zip压缩包.

运行R, 安装并载入bibliometrix包:

```R
install.packages("bibliometrix", dependencies = TRUE) #注意英文半角引号
library(bibliometrix)
```

然后运行命令:

```R
biblioshiny()
```

等待片刻即可在浏览器中使用图形界面的bibliometrix程序.

