---
layout: post
title: 基于R的统计分析
---

<!--more-->
 
首先,将数据整理为长列表的形式,并保存为`.csv`文件(逗号分隔).

将`.csv`文件加载到R中:

```R
data1 <- read.csv("path:\\path\\", header = TRUE or FALSE) #视有无列名而定.
data1
```
单因素方差分析(ANOVA):

```R
aov <- aov(value ~ treatment, data = data1) #不要忘记确认data1$treatment的属性是否为factor.
anova_test <- summary(aov)
anova_test
```

使用Tukey's HSD法进行多重比较:

```R
install.packages("agricolae")
library(agricolae)
test_tukey <- HSD.test(aov, "treatment", alpha = 0.05, group = TRUE)
test_tukey
```

将结果导出到csv文件中:

```R
sink("output.csv")
anova_test
tukey_test
sink()
```

在`C:\\user\\documents`文件夹中找到`output.csv`文件并打开, 选中第一列,依次选择
`数据->分列`菜单, 勾选空格作为分列符, 完成.

The end.
