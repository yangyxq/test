# test

如何将两个RMarkdown(.Rmd)文件合并成一个输出？

可按不同功能或任务分别建立Rmd文件，比如，有三个Rmd文件在同一个文件夹：carstest0.Rmd, carstest1.Rmd, carstest2.Rmd。

三个Rmd文件的各自功能分别是全局头设置功能、数据预处理、描述分析。

其中头设置中，需要有指定子Rmd文档的语句

如果你想要一个快速的方法来创建子Rmd文档的块：

rmd <- list.files(pattern = '*.Rmd', recursive = T, include.dirs = T) chunks <- paste0("{r child = '", rmd, "'}\n\n") cat(chunks, sep = '\n')

```{r child = 'carstest1.Rmd'}
```
```{r child = 'carstest2.Rmd'}
```
