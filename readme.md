# AtmosphericRefraction

## 简介

AtmosphericRefraction 是一个基于 NodeJS 开发的大气折射计算工具，可修正大气折射对地平高度所产生的影响。

## 安装

通过 npm 安装，在你的 node 项目目录下执行：

`npm i --save @behaver/atmospheric-refraction`

安装完成后，调用即可：

`const AtmosphericRefraction = require('@behaver/atmospheric-refraction');`

## 用例

```js
const AtmosphericRefraction = require('@behaver/atmospheric-refraction');

// 实例化大气折射对象
let ar = new AtmosphericRefraction({
  T: 23, // 海平面温度，单位：摄氏度
  P: 1018, // 海平面大气压强，单位：百帕
  apparentH: 23.456, // 视地平高度，单位：度
});

// 获取真地平高度，单位：度
let trueH = ar.trueH;

// 输出高度修正值
console.log(ar.R);
```

## API

`constructor(options)`

构造函数，接口同 init 方法

`init(options)`

初始化方法

规定参数：

* options.T 温度，单位：摄氏度
* options.P 大气压强，单位：毫巴/百帕
* options.apparentH 视地平高度，单位：度
* options.trueH 真地平高度，单位：度
* options.isStrict  是否精确修正（考虑气压、温度影响）

`set apparentH(h0)`

设置 视地平高度（单位：度）

`set trueH(h)`

设置 真地平高度（单位：度）

`set T(t)`

设置 温度设定（单位：摄氏度）

`set P(p)`

设置 大气压强设定（单位：百帕）

`set isStrict(isStrict)`

设置 是否进行精确修正

`get apparentH()`

获取 视地平高度（单位：度）

`get trueH()`

获取 修整大气折射后的真地平高度（单位：度）

`get r()`

获取 大气折射修正值（单位：度）

`get R()`

获取 大气折射修正值（包含温度和大气压强修正，单位：度）

`get T()`

获取 温度设定（单位：摄氏度）

`get P()`

获取 大气压强设定（单位：百帕）

`get isStrict()`

获取 是否进行精确修正设定

## 许可证书

The MIT license.