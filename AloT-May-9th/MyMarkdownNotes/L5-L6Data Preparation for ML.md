# L5-L6Data Preparation for ML

## IoT/DataPre/AIML之间的关系

![截屏2021-05-08 15.38.14](https://tva1.sinaimg.cn/large/008i3skNgy1gqb26wcembj30sy0aygnm.jpg)

## Preliminary

### CRISP-DM

1. Define a problem(Business Understanding)
2. Find the data

### python data structure

可以包含不同kind的elements.

![截屏2021-05-08 15.59.27](https://tva1.sinaimg.cn/large/008i3skNgy1gqb2syiqh2j30uo090gn4.jpg)

![截屏2021-05-08 15.59.53](https://tva1.sinaimg.cn/large/008i3skNgy1gqb2tejf87j30uo08wtaa.jpg)

### python data structure inadequacy

- Do things manually is very tedious.

![截屏2021-05-08 16.04.26](https://tva1.sinaimg.cn/large/008i3skNgy1gqb2y4qsisj30i40aq40b.jpg)

![截屏2021-05-08 16.04.38](https://tva1.sinaimg.cn/large/008i3skNgy1gqb2ycpxhxj30i40dkjtp.jpg)

## SciPy--Sigh Pie

- NumPy--Base N-dimensional array package
- Pandas-- Data preparation
- Matplotlib--Comprehensive 2D Plotting

![截屏2021-05-08 16.10.52](https://tva1.sinaimg.cn/large/008i3skNgy1gqb34t10zij30y409ctg2.jpg)

Equilibrium Capability:SQL-based Relational Database

## Series

- One-dimensional data structures

- Additional features:

  ![截屏2021-05-08 16.13.08](https://tva1.sinaimg.cn/large/008i3skNgy1gqb375sutqj30x40fq10p.jpg)

注意这里Python Series 和传统的1-dimensional Array的区别【points!PS】

**index (label)** is pointing to value

![截屏2021-05-08 16.17.13](https://tva1.sinaimg.cn/large/008i3skNgy1gqb3bfnhwuj30oc05i75t.jpg)

可以用这个index String Label 去travel through Series.

```python
s['b']
s[s>0]# fileter
```

使用字典也可以新建pandas Series

## DataFrame

![截屏2021-05-08 16.36.23](https://tva1.sinaimg.cn/large/008i3skNgy1gqb3veq1d8j30wk0nqdu8.jpg)

- Each column as one series

index 0:{color: blue, object: ball, price:1.2}

![截屏2021-05-08 16.40.34](https://tva1.sinaimg.cn/large/008i3skNgy1gqb3zrxij2j31ss0bgdn0.jpg)