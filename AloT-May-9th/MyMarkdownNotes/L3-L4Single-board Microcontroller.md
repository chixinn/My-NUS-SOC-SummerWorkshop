# Single-board Microcontroller

> [microbit](https://www.microbit.org/)

![截屏2021-05-08 13.11.47](https://tva1.sinaimg.cn/large/008i3skNgy1gqaxyhiwc3j30sy0ektb9.jpg)

## Overview

[micro:bit趣味教程](https://zhuanlan.zhihu.com/p/43887034)

[makecode Editor](https://makecode.microbit.org/)

Program the micro-controller

## Micro: bit as a reactive system

- React to external events
- Perform a computation

> 1. Event : React ;Event : React;Event : React ;So and so forth.
> 2. Responsive : concurrently.

### 理解并发

![截屏2021-05-08 13.34.16](https://tva1.sinaimg.cn/large/008i3skNgy1gqaylx1x1aj312u06ydhc.jpg)

Use time-sharing to achieve concurrency：scheduler

![截屏2021-05-08 13.36.15](https://tva1.sinaimg.cn/large/008i3skNgy1gqaynxkn2tj30sq0amn48.jpg)

- queue
- interrupt : poll

#### non-preemptive

Wait for execution

A 结束了才会执行B。

Why A calls sleep ,then we can execute B ins?

#### Event Driven Programming model

- On start
- Basic.forever loop: pause to allow others run

![截屏2021-05-08 13.46.57](https://tva1.sinaimg.cn/large/008i3skNgy1gqayz3pt02j30um0jin0l.jpg)

### Round-robin

![截屏2021-05-08 13.50.20](https://tva1.sinaimg.cn/large/008i3skNgy1gqaz2kq4mmj30sy0jiteu.jpg)

A 睡了就去sleep列了，醒了就再回来去排队。

lose the event only when you press the button faster than 6ms 

![截屏2021-05-08 14.06.05](https://tva1.sinaimg.cn/large/008i3skNgy1gqazj02a5rj30sy0ietai.jpg)

如果是这种情况，B是死循环，然后我再摁A，这个时候不会show number，但是counter还是在增加的.

### Variables and operators

![截屏2021-05-08 14.12.12](https://tva1.sinaimg.cn/large/008i3skNgy1gqazpco414j30sy0hsn6r.jpg)

#### Problem with src03.js

我们想要的是完整的4位，也就是即使我们random是123，我们也想要0123，我们random是24，我们也想要0024，这个问题怎么解决呢

`src03.js`

```javascript
let num = 0

basic.forever(function () {
    num = Math.randomRange(0, 9999)
    basic.showString("Win 4D ")
    basic.showNumber(num)
    basic.showString("...")
})
```

～ 看`src04.js`

```javascript
let num = 0
let str = ""

basic.forever(function () {
    num = Math.randomRange(0, 9999)
    str = "000" + num
    str = str.substr(str.length - 4, str.length)
    basic.showString("Win 4D " + str + "...")
})
```

> Micro:bit当然没有完整的js库了，所以我们只能manually。

### Basic input/Output

![截屏2021-05-10 12.35.28](https://tva1.sinaimg.cn/large/008i3skNly1gqd85ih6h7j30x60j6afs.jpg)

![截屏2021-05-10 12.35.53](https://tva1.sinaimg.cn/large/008i3skNly1gqd85tjd5uj30vc0jin6g.jpg)

### Sensors Input

![截屏2021-05-10 21.32.44](https://tva1.sinaimg.cn/large/008i3skNgy1gqdnoce3mnj30uu0ji0wd.jpg)

### Wireless Communication

**Key Points:**

![截屏2021-05-10 21.33.29](https://tva1.sinaimg.cn/large/008i3skNgy1gqdnp46bh4j30sc0c4tat.jpg)

BLE: connect micro:bit and 树莓派

### Radio Wireless Communication

![截屏2021-05-10 21.35.14](https://tva1.sinaimg.cn/large/008i3skNgy1gqdnqz0pfoj30vu0gs77d.jpg)

### Programming Radio Wireless Communication

#### 2 basic uses

for p2p radio communication between two or more micro:bit devices

#### Exchanging data

![截屏2021-05-10 21.41.51](https://tva1.sinaimg.cn/large/008i3skNgy1gqdnxutft5j30rq08gjsq.jpg)

Name value Pair

![截屏2021-05-10 21.40.30](https://tva1.sinaimg.cn/large/008i3skNgy1gqdnxigkynj30eo036mxu.jpg)

注意`string`位数的限制。

#### radio.receivedPacket

There is no clock in the micro:bit

Control information :time /serial/signal

![截屏2021-05-10 21.51.13](https://tva1.sinaimg.cn/large/008i3skNgy1gqdo7kmx7ij30yk0gind7.jpg)

![截屏2021-05-10 21.54.39](https://tva1.sinaimg.cn/large/008i3skNgy1gqdob5uju9j30mk0iy7g8.jpg)

#### Controlling another micro:bit

![截屏2021-05-10 21.57.25](https://tva1.sinaimg.cn/large/008i3skNgy1gqdoe1jep4j31ee0cs0yc.jpg)

这个在现实世界中可以模拟control the light

Only respond to the authorized command.

![截屏2021-05-10 21.58.21](https://tva1.sinaimg.cn/large/008i3skNgy1gqdof07jbmj30qw0s8jx8.jpg)

### Data Structure

Javascript Array