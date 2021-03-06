# 亲戚关系计算器

## 概要
亲戚关系是种非常复杂的人际关系，不是简简单单的叔叔阿姨爷爷奶奶就能通用了。这里我们使用开源的亲戚关系算法做个简单的网页。

## 功能设计
1. 分计算称呼和计算关系两种模式。
2. 计算称呼需要知道待计算的关系，使用者的性别（男|女）以及使用者是想计算对方称呼自己还是自己称呼对方。计算自己称呼对方的场景比较常见，设为默认值。
3. 计算关系需要知道待计算的称呼和使用者的性别（男|女）。
4. 亲戚关系虽然复杂，这里把基础关系作为计算器的按键，通过这些简单的单层关系，计算出复杂的亲戚关系。基础关系包括（父母 | 夫妻 | 兄弟 | 姐妹），这里设计8个元素按键，分别是「父」「母」「夫」「妻」「兄」「弟」「姐」「妹」，以及两个操作按键：「退格」用来删除前次输入，「清空」用来清空输入。
5. 一个输入框用来显示输入内容，一个区域用来展示计算结果。对于无计算结果的结果要给出默认输出。
6. 计算方式采用自动计算以减少用户输入。

## 程序设计

### 关系计算方法设计
这里我们使用开源的亲戚关系算法 [https://github.com/mumuy/relationship](https://github.com/mumuy/relationship)

安装依赖
```
npm install relationship.js
```
在 Vue 中使用一下语句来引入 relationship.js
```
import relationship from "relationship.js";
```
通过下面简单的调用即可得到计算结果
```
const options = {
    text, // 输入文本 如：爸爸的妈妈
    sex, // 性别 0: 女; 1: 男;
    type, // 模式 "default": 计算称呼; "chain": 计算关系;
    reverse // 称呼方式 false: 我称呼对方; true: 对方称呼我;
};

// 输出结果类型为字符串数组
const res = relationship(options);
```

### 界面设计
从上到下依次为通知区域，输入区域和结果区域共三个区域。

1. 通知区域主要展示一些说明信息，以及帮助等等。
2. 输入区域按照两种模式分成两个 tab 页。
    + 计算称呼 tab 需要单选性别（女|男）按钮，单选称呼方式（我称呼对方|对方称呼我）按钮，文本输入框，快捷关系输入按键组合
    + 计算关系 tab 需要单选性别（女|男）按钮，文本输入框
3. 结果区域根据输入区域的条件自动出结果，对于没有计算结果的给出默认结果（Sorry，我没有计算出来哦～）。

##### 参考文档
- [https://github.com/Ice-Hazymoon/MikuTools](https://github.com/Ice-Hazymoon/MikuTools)
- [https://github.com/mumuy/relationship](https://github.com/mumuy/relationship)