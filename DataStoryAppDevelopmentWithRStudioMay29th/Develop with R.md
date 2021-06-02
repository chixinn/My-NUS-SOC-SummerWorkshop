# Develop with R

## Grasp with R

![Screen Shot 2021-05-29 at 10.21.27](https://tva1.sinaimg.cn/large/008i3skNly1gqz31s34cfj308c022aaa.jpg)

![Screen Shot 2021-05-29 at 10.21.40](https://tva1.sinaimg.cn/large/008i3skNly1gqz31y1gaaj60ga06qwf702.jpg)

注意`R`里面有arrow assign

这里`a`就相当于`object`了(writing to memory)

```R
a<-"Hello World!"
rm(a)
```

- Environment : store Objects.
- History: store all the line by line we type in console.
- How to look through the manual
- ![Screen Shot 2021-05-29 at 10.27.35](https://tva1.sinaimg.cn/large/008i3skNly1gqz38zn9n2j30za0p87aq.jpg)

- R will use the location where R studio is installed as  a working directory.
- ![Screen Shot 2021-05-29 at 10.37.34](https://tva1.sinaimg.cn/large/008i3skNly1gqz3ijb4d7j30ye0fmtdr.jpg)

去Tools->Global Options可以更改R当前的工作目录。

## Data Types

- Integer 类型的1L和1
- Logical/integer/numerics/complex
- ![Screen Shot 2021-05-29 at 10.45.06](https://tva1.sinaimg.cn/large/008i3skNly1gqz3qe3ohbj307s060jro.jpg)

- ![Screen Shot 2021-05-29 at 10.49.44](https://tva1.sinaimg.cn/large/008i3skNly1gqz3v81v62j30880ae3zc.jpg)

in R: the first index is 1.

-  Do a search instead of writing a function yourself

  Very likely someone has written a particular package

```R
install.packages("stringr")
?stringr
```

## Data Structures

Vector/matrix/list/data.frame

### Vector

- Vector: 1-dimension sequence `a<-c(2,7,10)`;

  `4:20`,这里`:`相当于to的意思;` seq(1,100,2)`;`seq(1,100,length.out=40)`;` rep(7,10)`;

- ![Screen Shot 2021-05-29 at 10.59.50](https://tva1.sinaimg.cn/large/008i3skNly1gqz45w8ni6j60ds03cmxq02.jpg)



- ![Screen Shot 2021-05-29 at 11.00.44](https://tva1.sinaimg.cn/large/008i3skNly1gqz46ms7jgj306y03cq2z.jpg)



- R is case-sensitive:即R对大小写是敏感的，不认识True嘛 ，咱也可以理解。

- Important:All the elements in vector must be the same datatype(automatically convert to the same type)

  ![Screen Shot 2021-05-29 at 11.05.11](https://tva1.sinaimg.cn/large/008i3skNly1gqz4bax2ugj3082046wek.jpg)

- Coerce():Methods for Coercing an Object to a Class

  Logical<integer<numeric<complex<character

- ![Screen Shot 2021-05-29 at 11.07.21](https://tva1.sinaimg.cn/large/008i3skNly1gqz4dimwgoj306y046glm.jpg)

注意这里面是一个automatically upgrade.

- ![Screen Shot 2021-05-29 at 11.10.35](https://tva1.sinaimg.cn/large/008i3skNly1gqz4gvvup8j606y06wq3602.jpg)

注意这里的负号在R里面表示的是exclude

#### Get element

- 索引：a[c(1,2)] 注意用vector的嵌套索引
- Conditional checking
- ![Screen Shot 2021-05-29 at 11.14.16](https://tva1.sinaimg.cn/large/008i3skNly1gqz4kpyhwcj30ak03ct8y.jpg)

Filtering

```R
a<-c(1,3,4)
furniture <- c("desks", "tables", "chairs")
names(a) <- furniture
a
##  desks tables chairs 
##      1      3      4
```

- Do not need a for-loop![Screen Shot 2021-05-29 at 11.15.23](https://tva1.sinaimg.cn/large/008i3skNly1gqz4lup31pj309a02saa5.jpg)

- ![Screen Shot 2021-05-29 at 11.17.54](https://tva1.sinaimg.cn/large/008i3skNly1gqz4ohwqn5j30ik06wt9g.jpg)太神奇了R中短的那个就会循环。

### Matrix

- In column first

  ![Screen Shot 2021-05-29 at 11.19.59](https://tva1.sinaimg.cn/large/008i3skNly1gqz4qo0uipj30i00d4gn0.jpg)

  Matrix is a vector(every col and row); matrix has the same requirements as the vector

- ![Screen Shot 2021-05-29 at 11.22.32](https://tva1.sinaimg.cn/large/008i3skNly1gqz4tbk6mnj309a07s0tm.jpg)

  First row/second row

  m[c(1,2),c(2,3)]: first row and second row; second col and third col

### List

#### List v.s. vector

- a<-list(Name="David",Age=37,Num.Children=2,Children=c("John","Alice"))

   Allow elements in different types

  ![Screen Shot 2021-05-29 at 11.26.08](https://tva1.sinaimg.cn/large/008i3skNly1gqz4x1dzu8j30oe0d60tt.jpg)

`a$`的使用:![Screen Shot 2021-05-29 at 11.26.54](https://tva1.sinaimg.cn/large/008i3skNly1gqz4xupyscj309a05sq36.jpg)

#### Get element from list

In list: a[4]means a sublist

![Screen Shot 2021-05-29 at 11.28.34](https://tva1.sinaimg.cn/large/008i3skNly1gqz4zlm4f9j309a07qmxn.jpg)

所以，用a[4] get element 和a[[4]]得到的结果是不一样的。

### DataFrame

- 查看DataFrame中的某一列：companies$Country
- DataFrame is a list of vectors.
- Most features we learn from matrix can be applied to DataFrame
- str(companies)
- nrow(companies)
- ncol(companies)
- Summary(companies): give basic statistics

---

- We want to find companies whose sales are above 200B.

  ![Screen Shot 2021-05-29 at 13.17.42](https://tva1.sinaimg.cn/large/008i3skNly1gqz85871enj30pq03yaaq.jpg)
  
  我这个地方错的根本原因是这应该是行，少了一个`,`

  Get results from True or False  ![Screen Shot 2021-05-29 at 13.18.20](https://tva1.sinaimg.cn/large/008i3skNly1gqz85uf4otj30m607qgn6.jpg)

Only want to get the name:`companies[companies$Sales...billion.>200,"Company"]`;Only want to get the name:`companies[companies$Sales...billion.>200,"2"]`【Either go by name or the index】

![Screen Shot 2021-05-29 at 13.21.55](https://tva1.sinaimg.cn/large/008i3skNly1gqz89jf0axj30pq036aaj.jpg)

这个result也是data frame，所以就可以用`$`了

`res<-big.companies<-companies[companies$Sales...billion.>200 & companies$Location=='Asia',"Company"]`

- 如果想获得最大的Sales的companies怎么办呢？

  ```R
  > max(companies$Sales...billion.)
  [1] 469.2
  > companies[companies$Sales...billion.==max(companies$Sales...billion.),"Company"]
  [1] "Wal-Mart Stores"
  > which.max(companies$Sales...billion.)
  [1] 15
  > companies[which.max(companies$Sales...billion.),"Company"]
  [1] "Wal-Mart Stores"
  ```

- Top-k

  ```R
  head(companies[order(-companies$Sales...billion.),],10)$Company
  ```

  average Value of everySale in the Top10 here.

  ```R
  > companies.top.10<-head(companies[order(-companies$Sales...billion.),],10)
  > mean(companies.top.10$Sales...billion.)
  [1] 339.02
  > reafa<-order(companies$Sales...billion.)
  > class(reafa)
  [1] "integer"
  ```

- Profit margin(profit/sale)

  37.8/134.8 ：everyMoney ICBC wins is going to be its profit

- How to add a Profit Margin Column

  Add a new col from original Data:

  ![Screen Shot 2021-05-29 at 13.38.58](https://tva1.sinaimg.cn/large/008i3skNly1gqz8s2hapzj30qy12ggt3.jpg)

  Add a new col from totally New Data:

  ```R
  ID<-1:nrow(companies)
  companies<-cbind(companies,ID)
  ```

- Delete a col:

  ```R
  companies$ID<-NULL
  ```

  

#### Column Factor

When a data has limited categories: categorical data

Store as charter:

1. 计算机存字符串跟数字比占内存
2. 线性回归时：就得build dummy variable

```R
> companies$Continent<- as.factor(companies$Continent)
> class(companies$Continent)
[1] "factor"
> as.integer(companies$Continent)
```

Factor : The value is sequence here, 同样的，这里的sequence也可以自己定义

```R
> levels(companies$Continent)
[1] "Africa"        "Asia"          "Europe"       
[4] "North America" "Oceania"       "South America"
> levels(companies$Continent)<-c("Asia","Africa","Europe","South America","Oceania","North America")
> levels(companies$Continent)
[1] "Asia"          "Africa"        "Europe"       
[4] "South America" "Oceania"       "North America"ca"
```

![Screen Shot 2021-05-29 at 13.56.11](https://tva1.sinaimg.cn/large/008i3skNly1gqz996r6xaj30l2022758.jpg)

- table() counter each continent

---

Install package first and then call the library to use it

---

- 问题1:Get this data

![Screen Shot 2021-05-29 at 14.06.05](https://tva1.sinaimg.cn/large/008i3skNly1gqz9ji0wghj30ic05kq49.jpg)

![Screen Shot 2021-05-29 at 14.06.18](https://tva1.sinaimg.cn/large/008i3skNly1gqz9jpa5emj30m206a417.jpg)

这样处理有什么问题？

1. 很多companies的冗余
2. Set1/set2/set3这种intermediate set会占内存 中间的就useless了

所以dlypr就帮我们解决了这个问题

> Pipe Operator

Supply companies as the source

Link up all the pipes together to become 1 complete operation

![Screen Shot 2021-05-29 at 14.14.08](https://tva1.sinaimg.cn/large/008i3skNly1gqz9rvj3lij30m202k402.jpg)

![Screen Shot 2021-05-29 at 14.19.00](https://tva1.sinaimg.cn/large/008i3skNly1gqz9wwae25j30m2088dio.jpg)

这样就不会产生rubbish 了

---

- 问题2: Get this da-ta: **Find the average sales of the top companies by continents**

  ```R
  > companies %>% group_by(Continent) %>% summarise(Avg.Sales=mean(Sales...billion.))
  # A tibble: 6 x 2
  <
    Continent     Avg.Sales
    <chr>             <dbl>
  1 Africa             7.07
  2 Asia              16.1 
  3 Europe            25.1 
  4 North America     19.6 
  5 Oceania           14.9 
  6 South America     16.9 
  ```
  
  ```R
  companies %>% group_by(Continent) %>% summarise(Max.Profit = max(Profits...billion.), No.Companies = n(),  Avg.Sales = mean(Sales...billion.))
  ```
  
  这里的max()啥啥，n()啥啥，都是自己可以写的函数。



---

### Requirement

![Screen Shot 2021-05-29 at 14.28.49](https://tva1.sinaimg.cn/large/008i3skNly1gqza76jdvsj30sq0acdjg.jpg)

````R
English <- read.csv("PSLE/English.csv")
English$subject <- "English"
colnames(English) <- c("year","race","percentage","subject")
Math <- read.csv("PSLE/Math.csv")
colnames(Math) <- c("year","race","percentage")
Math$subject <- "Math"
MotherTougue <- read.csv("PSLE/MotherTougue.csv")
colnames(MotherTougue) <- c("year","race","percentage")
MotherTougue$subject <- "MotherTougue"
Science <- read.csv("PSLE/Science.csv")
colnames(Science) <- c("year","race","percentage")
Science$subject <- "Science"
PSLE <- do.call("rbind", list(English, Math, MotherTougue,Science))
> View(English)
> PSLE <- do.call("rbind", list(English, Math, MotherTougue,Science))
````

- 数据集有什么问题吗？

  How to在种族里 remove `Overall`

  ```R
  PSLE<-PSLE[PSLE$race!='Overall',]
  ```

- How many unique years of data? 

  ```R
  > unique(PSLE$year)
  > length(unique(PSLE$year))
  ```

  用level不好，不要把year这种number变量convert to level这种

- Find all the data where Malay students have percentage > 95

```R
PSLE[PSLE$race=='Malay' & PSLE$percentage>95,]
```

![Screen Shot 2021-05-29 at 15.00.41](https://tva1.sinaimg.cn/large/008i3skNly1gqzb4c5e9zj30jm0200tb.jpg)

![Screen Shot 2021-05-29 at 15.01.29](https://tva1.sinaimg.cn/large/008i3skNly1gqzb55iyqqj30m40aoq5f.jpg)

---

## Practice:tydyr

1. Wide format

   ![Screen Shot 2021-05-29 at 15.37.10](https://tva1.sinaimg.cn/large/008i3skNly1gqzc6a1ajjj30m402u3z8.jpg)

![Screen Shot 2021-05-29 at 15.39.36](https://tva1.sinaimg.cn/large/008i3skNly1gqzc96e0pnj30n20zogrr.jpg)

## Read files

### Xml v.s. csv

- csv:comma-seperated data: all works across different platforms
- Xml: hierarchical(半结构化) ; csv: flat

### Explore xml in R(xml Tree)

- `dta <- xmlParse("Session 3/books.xml")`

- `root <- xmlRoot`

- `children <- xmlChildren`

- ```R
  > books <- xmlChildren(nodes[[2]])
  > class(books)
  [1] "XMLInternalNodeList" "XMLNodeList"    
  ```

- 如果我们已经知道xml的structure了，我们当然就不用1by1了，就可以directly Get了

- Attribute:![Screen Shot 2021-05-29 at 15.58.36](https://tva1.sinaimg.cn/large/008i3skNly1gqzcsr143tj30m4016wev.jpg)

  `books <- getNodeSet(dta,"/Library/catalog/book")` find based on Structure as well as attribute

```R
data <- xmlParse("books.xml")
data
root <- xmlRoot(data)
root
nodes <- xmlChildren(root)
nodes[1]
nodes[2]
nodes[[2]]
books <- xmlChildren(nodes[[2]])
class(books)
books[[1]]
books[[2]]
books <- getNodeSet(data,"/library/catalog/book")
books
books <- getNodeSet(data,"/library/catalog/book[@type='SoftCover']")
books
books <- xmlToDataFrame(books)
View(books)
```

会损失attributes信息

> Xml: data communication (share data) ;html: data display
>
> But recent years JSON is more popular now.(standard for API / client and Server)

[https://data.gov](获取Data的途径除了Kaggle)

### 用API和数据网站导入数据到R

https://data.gov.sg/dataset/carpark-availability

![Screen Shot 2021-05-29 at 16.13.35](https://tva1.sinaimg.cn/large/008i3skNgy1gqzd86ua54j30u00w4n1e.jpg)

复制这个https://api.data.gov.sg/v1/transport/carpark-availability

```R
theurl <- "http://apps.saferoutesinfo.org/legislation_funding/state_apportionment.cfm"

#Read the whole page into our local computers
url <- curl(theurl)
urldata<-readLines(url)

#use readHTMLTable function to extract the table out
data <- readHTMLTable(urldata,  stringsAsFactors = FALSE)
```

