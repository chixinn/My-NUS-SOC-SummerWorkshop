# L2:  Jupyter NB

- Input: list

  Output:dictionary

- Magic commands:[不是python的，是very specific to Jupter NB的]

  `%` `%timeit L`:

  Loading extranal .py file

- 【PS】python List is very flexible but slow!

- ![截屏2021-05-15 13.31.09](https://tva1.sinaimg.cn/large/008i3skNgy1gqj1uw40cbj317g0t4141.jpg)

【PS】一个numpy array 是内存中一个连续块，并且array里的元素都是同一类（例如整数）。所以一旦确定了一个array，它的内存就确定了，那么每个元素（整数）的内存大小都确定了（4 bytes）。

list完全不同，它的每个元素其实是一个地址的引用，这个地址又指向了另一个元素，这些元素的在存里不一定是连续的。所以list其实是只能塞进地址的“数组”，而且由于地址不用连续，每当我想加入新元素，我只用把这个元素的地址添加进list。

- Array slicing:![截屏2021-05-15 13.47.16](https://tva1.sinaimg.cn/large/008i3skNgy1gqj2blrtnhj31f80rkgq5.jpg)

- Sub_array is not a copy。如果sub-array变了，原来那个也变了。如果我想copy我需要include`

  ```
  x2_sub_copy = x2[:2, :2].copy()
  print(x2_sub_copy)
  ```

  ![截屏2021-05-15 13.51.30](https://tva1.sinaimg.cn/large/008i3skNgy1gqj2fzzg4uj30gk0oegmv.jpg)

- `grid=np.arange(1,10)`

  怎么把array变成column vector？

  `grid.T`对2-dimensional array有用。

- axis=1;vertical

- Universal functions ：often被people ignore.

  【在实验楼里也有自学到】【PS】

- ![截屏2021-05-15 14.06.43](https://tva1.sinaimg.cn/large/008i3skNgy1gqj2vu2gp9j31j00hywps.jpg)【PS】

  Big difference in efficiency

[为什么python慢](https://www.163.com/dy/article/G8436BK00511FQO9.html])

> This vectorized approach is designed to push the loop into the compiled layer that underlies NumPy, leading to much faster execution

- ufuncs Broadcasting：

  [广播机制](https://blog.csdn.net/iteye_3004/article/details/82293818)

---

## Pandas

![Screen Shot 2021-05-15 at 15.33.31](https://tva1.sinaimg.cn/large/008i3skNgy1gqj5e42odqj30qy0d4q53.jpg)

- Index  can be non-sequential
- ![Screen Shot 2021-05-15 at 15.36.23](https://tva1.sinaimg.cn/large/008i3skNgy1gqj5h3nw82j30sk0gcq6h.jpg)

- Pandas offers relational algebra:merge with many join types...
- one-to-one join :name of employee is used as a key automatically

- Concat v.s. merge concat:different types of join cannot do.

- Merge with key is helpful.

- [pandas中concat(), append(), merge()的区别和用法](https://zhuanlan.zhihu.com/p/70438557)

  Merge和key有关

## Timeseries in Python

![Screen Shot 2021-05-15 at 16.12.56](https://tva1.sinaimg.cn/large/008i3skNgy1gqj6j57gp8j30ko0s0q77.jpg)

`date+np.arange(12)`

`date.strftime('%A')`

- Use date time as index is sometimes very important【PS】
- ![Screen Shot 2021-05-15 at 16.17.10](https://tva1.sinaimg.cn/large/008i3skNgy1gqj6njdn7oj30um0jun3s.jpg)

【PS】import live data from markets.

- Work from pandas-datareader
- 'BA‘:annual
- [python timeseries](https://jakevdp.github.io/PythonDataScienceHandbook/03.11-working-with-time-series.html)
- Forward fill vs Backward fill

---

- Tutorial

- ![Screen Shot 2021-05-15 at 17.01.46](https://tva1.sinaimg.cn/large/008i3skNgy1gqj7y0ecugj30ti0h841p.jpg)

