# AloT: Artifial Intelligence of Things

- Hardware Prototyping
- AI Machine Learning
- Software Engineering

## Opening Vignette

- Nest Labs

---

【PS】对hardware的不感兴趣：

Project/板子/传感器的不感兴趣？

不能线下深表遗憾，表达对新国立的渴望

## Overview

AloT/real-time datatimeline

AI ML on hardware.

### Pervasive/Ubiquitous Computing

Computer: 我们自己做别的，computer帮我们做其他事，quiet invisible servant.

![截屏2021-05-08 10.05.28](https://tva1.sinaimg.cn/large/008i3skNgy1gqaskrfvd0j30zm0n2qn5.jpg)

Smart coffee maker: we see the coffee maker but we don't see the computer.

> Smart mat watches out for the elderly

![截屏2021-05-08 10.10.08](https://tva1.sinaimg.cn/large/008i3skNgy1gqaspipncrj30e209oq8f.jpg)

### Hard-ware  technology constrains

Hardware progress commercially viable to make visions possible

## IoT?

Internet: network of computer network.

Internert:在链接电脑前，还链接其他的东西。all physical devices and other items

>  Connected devices/smart devices

IoT和6G

### Characteristic1:For a set of application

![截屏2021-05-08 10.21.30](https://tva1.sinaimg.cn/large/008i3skNgy1gqat1cl7myj30wm0bin5z.jpg)

### Characteristic2: loT system：sensors and actuators

Sensors and actuators

![截屏2021-05-08 10.26.29](https://tva1.sinaimg.cn/large/008i3skNgy1gqat6jxblpj30ka0j2tiy.jpg)

![截屏2021-05-08 10.28.21](https://tva1.sinaimg.cn/large/008i3skNgy1gqat8i831ij31180qqqje.jpg)

- Edge processor是什么？

  Collect?Do processing at local level

- Small 的system是不需要edge processor, go straight to the cloud.

![截屏2021-05-08 10.31.41](https://tva1.sinaimg.cn/large/008i3skNgy1gqatbyrtt7j31180l415m.jpg)

这个图式很形象的解释了edge缓解latency的原因。

4.5G/5G的区别在架构里的Network Layer

![截屏2021-05-08 10.38.09](https://tva1.sinaimg.cn/large/008i3skNgy1gqatiy12ghj31jn0u0no1.jpg)

## AIoT?

How can we make IoT system smart?

【可爱片段:D

![截屏2021-05-08 10.46.03](https://tva1.sinaimg.cn/large/008i3skNgy1gqatquw3slj30kk0c0aco.jpg)

> CON'T 是 continued的缩写，一般用在标题中，表示“继续”的意思。

## AloT

- loT System: focus on building real-time sensor data pipeline
- AloT System: further integrates with AI machine Learning

AloT tell you rain before it actually rains.

AI : expect the computer to do sth as human.

> Main focus: Machine Learning

### ML

Build model on historical data/sample data / training dataset

Autonomous decision:注意理解这里面的autonomous是什么意思，就是我们不可能programmly 考虑所有input,即所有roads的场景。

![截屏2021-05-08 19.55.41](https://tva1.sinaimg.cn/large/008i3skNgy1gqb9mq7b1uj30nu06w443.jpg)

> Intuitively: ML 就是去找一个mapping 映射，from input to output.

#### Two-main category--A->B mapping

这里说的两类是什么呢

- Supervised Learning

  Training data contains B

- Unsupervised Learning

  Training data does not contain RB

### AIoT=IoT+AI : the Whole is greater than the Sum of the Parts

- ML 的 conventional data: Subjective Data
- AIoT system的 sensor data: Objective Data

注意这面的这两种data 的区别。

![截屏2021-05-08 20.05.35](https://tva1.sinaimg.cn/large/008i3skNgy1gqb9x0iuesj30zw0mskbp.jpg)

Use the sensor data to train ML model



## Data Pipeline

### The importance of Data Preparation

![截屏2021-05-08 12.33.17](https://tva1.sinaimg.cn/large/008i3skNgy1gqawugg1hsj30ua0cyq5c.jpg)

### Data Pipeline System Structure

![截屏2021-05-08 20.12.36](https://tva1.sinaimg.cn/large/008i3skNgy1gqba4sgpz9j30ka0csgrm.jpg)

Data Pipeline goes from left to right. 

In IoT Systems: data is collected by the sensors automatically in the real-time. AloT do **AI -ML + Realtime Sensor Data.**

## AIoT System : Real-world Case Study.

救命，这个实战模拟好有趣【PS】

【PS:我以为自己的动手能力不行，但实际觉得很有趣？】

- Breadboard

### Weather Forecast Case Study

- Temperature,Humidity(A) -> Rain(B)
- We need a labelled dataset for training :automatically label.

> Cold start problem: We will not predict correctly if we don't have sufficient historical data。**那在这个场景中如何解决cold-start problem的问题？**
>
> We can use a rain/moisture sensor to detect rain in conjunction with temperature and humidity sensors.

### High-level architecture

1. Sensor Node/Hub -> Cloud Server（树莓派， also Edge Processor）
2. Cloud Server store the data in database
3. Python Data Preparation : seconds-> minutes data
4. Python Analytics Program: sliding window to choose
5. Python Analytics Web Service:  input current temperature and humidity and gets a prediction(call the Python Analytics Program Backend)

---

![截屏2021-05-09 10.30.59](https://tva1.sinaimg.cn/large/008i3skNgy1gqbyxj4hzoj30zk0mkkjl.jpg)

- DHT 11 temperature sensor
- MH-RD moisture sensor

![截屏2021-05-09 10.24.23](https://tva1.sinaimg.cn/large/008i3skNgy1gqbyqlw2qkj30uc0jqtoc.jpg)

> 注意top和bottom的Edge Processor的对比，一旦我们解决了cold Start 问题以后，下面的数据就只有temperature 和moisture data了。

---

## Q&A

1. How much data is sufficient -> accuracy ; the more training data ,the more accuracy.

2. IoT sensors: automatic labelling【PS跟传统的机器学习也不一样】

3. ![截屏2021-05-09 10.31.58](https://tva1.sinaimg.cn/large/008i3skNgy1gqbyyj8cdqj30d60cqabd.jpg)

   After the model is trained, the boundary is determined automatically.