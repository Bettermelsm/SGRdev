# SGRdev
The softwares which were developed by R and used for Sengene Technology Co.,Ltd.


>echo = FALSE：隐藏代码，但运行代码并产生所有输出，曲线图，警告和消息。</br>
eval = FALSE：显示代码，但不对其进行评估。</br>
fig.show = “hide”：隐藏图。</br>
message = FALSE：防止软件包在加载时打印消息。这也抑制了函数生成的消息。</br>
results = “hide”：隐藏打印输出。</br>
warning = FALSE：防止软件包和功能显示警告。</br>


```{r,echo=FALSE,warning=FALSE}
library(readxl)
library(gt)

df <- read_excel("RMD1.xlsx", sheet = 1)

df %>%
  gt() %>%
  tab_style(
    style = cell_borders(sides = "all", weight = px(1), color = "gray"),
    locations = cells_body()
  ) %>%
  tab_options(table.font.size = "14px")

```



```{r,echo=FALSE,warning=FALSE}
library(readxl)
library(flextable)

df <- read_excel("RMD1.xlsx")
ft <- flextable(df)
ft <- autofit(ft)

ft

```
#主推DT样式，既有排序，又有搜索，还有分页
```{r,echo=FALSE,warning=FALSE}
library(readxl)
library(DT)

df <- read_excel("RMD1.xlsx")
datatable(df, options = list(pageLength = 10, autoWidth = TRUE))
```


```{r,echo=FALSE,warning=FALSE}
library(readxl)
library(reactable)

df <- read_excel("RMD1.xlsx")
reactable(df, striped = TRUE, bordered = TRUE, highlight = TRUE)

```



