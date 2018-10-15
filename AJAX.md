什么是AJAX？
  > “Asynchronous Javascript And XML”（异步JavaScript和XML），

> 并不是新的技术，只是把原有的技术，整合到一起而已。 

		   1.使用CSS和XHTML来表示。
		   2.使用DOM模型来交互和动态显示。
		   3.使用XMLHttpRequest来和服务器进行异步通信。
		   4.使用javascript来绑定和调用。

* 有什么用?

> 咱们的网页如果想要刷新局部内容。 那么需要重新载入整个网页。用户体验不是很好。  就是为了解决局部刷新的问题。 保持其他部分不动，只刷新某些地方。

##数据请求

		1.创建对象
			function ajaxFunction() {
		var xmlHttp;
		try { // Firefox, Opera 8.0+, Safari
			xmlHttp = new XMLHttpRequest();
		} catch (e) {
			try {// Internet Explorer
				xmlHttp = new ActiveXObject("Msxml2.XMLHTTP");
			} catch (e) {
				try {
					xmlHttp = new ActiveXObject("Microsoft.XMLHTTP");
				} catch (e) {
				}
			}
		}

		return xmlHttp;
	}
		

		2.发送请求
	//执行get请求
	function get() {
		//1.创建xmlhttprequest对象
		var requset = ajaxFunction()
		
		//2.发生请求
		/*
		参数一：请求类型 GET or POST 
		参数二：请求的路径
		参数三：是否异步  true or false
		*/
		requset.open("GET","/AjandJQ/DemoServlet01",true);
		requset.send();
	}
