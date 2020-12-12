# Photovoltaic_electronic_communication_control
谈谈这个软件的缺点：

1.软件界面不够美观；

2.平常使用界面会比较卡顿；

3.数据处理能力不够：

如：1.读取风光互补寄存器超过45个，数据会卡顿；

   2.读取浮点数据处理精度不足；主要体现在“读取环境模拟平台数据-风速”、“向PLC读取智能电表的数据”。
    
4.填写M区数据需要一个一个修改；

<h3>下面我来说说改进的建议：<h3>

1.软件界面美观的问题：多参考一些软件的布局；

2.软件界面卡顿：由于数据的处理都是在主线程进行的，大量数据收发的时候会导致界面卡顿；

解决办法：改用多线程处理数据，关于多线程的用法可以参考https://www.cnblogs.com/dotnet261010/p/6159984.html

3.数据处理能力不够：这个问题发生在浮点数处理上，解决办法就是“改变原来浮点数处理的算法”；

一下是改进的浮点数处理算法：(可以精确到小数点后四位)

参考库：Floating-point-data-processing(回到主页就可以看见，中文名：浮点数处理)；

或者点击链接：https://github.com/GitHub-yiming/Floating-point-data-processing

4.填写M区数据需要一个一个修改：推荐的解决办法是，当数值改变的时候，识别当前的数值，并且增加，自动追加到后面的文本框，这样就不用一个一个手动输入了；

