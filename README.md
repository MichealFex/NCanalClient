# NCanalClient

## 作用

基于C#.net实现的阿里canal的客户端,针对于服务端进行连接消费使用

## 示例

在 `/NCanalClient/TempClass.cs` 文件中有简单使用该客户端的一个实例,从服务端拿到数据后的解析方式.

启动入口在 `NCannal.Test`中.

## 后~~

由于没有考虑软件设计,仅仅从实现角度出发写的该client,其实有好多可以优化的.不过我比较懒,所以就没有然后了

## 提示

* 经生测试,获取到的消息需要确认消费掉,如果不确认,服务端会将该消息存在内存中,数据量多了后

* 会产生Canal主进程运行,但是对应的实例却死掉.造成无法长期进行服务,所以一定要注意*确认消息消费*

* 由于canal服务端的时间戳格式为13位长度.正常mysql时间戳是10位,.net默认也是10位,所以java会将mysql的时间戳后面拼接三个"0"