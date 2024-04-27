# 1. Apache ECharts

## 1.1 介绍

Apache ECharts 是一款基于 Javascript 的数据可视化图表库，提供直观，生动，可交互，可个性化定制的数据可视化图表。
官网地址：<https://echarts.apache.org/zh/index.html>

![image-20230101153041348-zoom:50%;](assets/image-20230101153041348.png)

**常见效果展示：**

1). 柱形图

![image-20230101153748714-zoom:50%;](assets/image-20230101153748714.png)

2). 饼形图

![image-20230101153230868-zoom:50%;](assets/image-20230101153230868.png)

3). 折线图

![image-20230101153824086-zoom:50%;](assets/image-20230101153824086.png)

**总结：**不管是哪种形式的图形，最本质的东西实际上是数据，它其实是对数据的一种可视化展示。

## 1.2 入门案例

Apache Echarts官方提供的快速入门：<https://echarts.apache.org/handbook/zh/get-started/>

**效果展示：**

![image-20230101155524477-zoom:50%;](assets/image-20230101155524477.png)

**实现步骤：**

1). 引入echarts.js 文件(当天资料已提供)

2). 为 ECharts 准备一个设置宽高的 DOM

3). 初始化echarts实例

4). 指定图表的配置项和数据

5). 使用指定的配置项和数据显示图表

**代码开发：**

```html
<!DOCTYPE html>
<html>
  <head>
    <meta charset="utf-8" />
    <title>ECharts</title>
    <!-- 引入刚刚下载的 ECharts 文件 -->
    <script src="echarts.js"></script>
  </head>
  <body>
    <!-- 为 ECharts 准备一个定义了宽高的 DOM -->
    <div id="main" style="width: 600px;height:400px;"></div>
    <script type="text/javascript">
      // 基于准备好的dom，初始化echarts实例
      var myChart = echarts.init(document.getElementById('main'));

      // 指定图表的配置项和数据
      var option = {
        title: {
          text: 'ECharts 入门示例'
        },
        tooltip: {},
        legend: {
          data: ['销量']
        },
        xAxis: {
          data: ['衬衫', '羊毛衫', '雪纺衫', '裤子', '高跟鞋', '袜子']
        },
        yAxis: {},
        series: [
          {
            name: '销量',
            type: 'bar',
            data: [5, 20, 36, 10, 10, 20]
          }
        ]
      };

      // 使用刚指定的配置项和数据显示图表。
      myChart.setOption(option);
    </script>
  </body>
</html>
```

**测试：**(当天资料中已提供)

![image-20230101160244104-zoom:50%;](assets/image-20230101160244104.png)

使用浏览器方式打开即可。

**总结：**使用Echarts，重点在于研究当前图表所需的数据格式。通常是需要后端提供符合格式要求的动态数据，然后响应给前端来展示图表。

