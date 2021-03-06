[对RTMP视频流进行BitmapData.draw()出错的解决办法](http://zengrong.net/post/1483.htm)

在对Flash Media Server中的视频流使用BitmapData.draw()进行绘制的时候，会抛出这样异常：

>cannot access rtmp://xxxxx. No policy files granted access.
>at flash.display::BitmapData/draw()

这个错误出现的原因是，客户端（swf）没有权限复制NetStream中的原始视频数据。看提示，是需要一个策略文件。

但是，在FMS服务器上无法放置策略文件，FMS也不能像Socket服务器那样发送策略文件给客户端，这种情况应该怎么处理呢？

**答案在这里：**

<http://help.adobe.com/en_US/flashmediaserver/ssaslr/WS5b3ccc516d4fbf351e63e3d11a11afc95e-7ec3SSASLR.html#WS5b3ccc516d4fbf351e63e3d11a11afc95e-7fcbSSASLR>

**只需要FMS在同意client连接后，为其设置videoSampleAccess属性即可。videoSampleAccess的设置方式与readAccess相同。**

范例：

	<pre lang="javascript">
	application.onConnect = function($client)
	{ 
		application.acceptConnection($client);
		//设置成"/"，允许所有路径
		client.videoSampleAccess = "/"; 
	}
	</pre>

