# R-selfCheck&Revision

## Amazing!!!其他啥都能忘了快捷键也不能忘

```R
txt <- 1-2i
```

所以这里这个`<-`怎么打出来呢，我是mac平台，所以就是`option -`即可，真神奇

## Fundamental

1. Coerce

   R的vector必须是同一种类型的数据，不同类型的数据合在一块就会发生 向地位最高的那个转嘛。

2. R里面这个VectorNaming好生神奇且捉摸不透:D

3. Self-Check1.html里面有相关的练习题

## Data Wrangling

1. 我记得MIT那个Missing Semester里面也有DataWrangling来着:D 那真是一门好课呀~

   Data Wrangling到底是什么： data-processing & Transformation 

2. `Data Frame` take vectors`c()` as parameters.

3. The` c() `vector function can also be used to subset multiple portions of the Data Frame.

4. 总感觉无论是`R`还是`Python` return index用好了真的很神奇`i_max <- which.max(df$age)`

5. Data Frame Indexing：用logic进行index的定位。We can use logical operators to find specific cases in our Data Frame. For example, people taller than 171 cm, the average male height in Singapore.

   生成`df`的代码：

   ```R
   name <- c("Anne", "Pete", "Frank", "Julia", "Cath")
   age <- c(28, 30, 21 ,39, 35)
   child <- c(FALSE, TRUE, TRUE, FALSE, TRUE)
   df <- data.frame(name, age, child)
   height <- c(163, 177, 163, 162, 157)
   df$height <- height
   tom <- data.frame(name = "Tom", age = 37,
   child = FALSE, height = 183)
   rbind(df, tom)
   df
   index <- df$height > 171
   df$name[index]  
   ```

   



