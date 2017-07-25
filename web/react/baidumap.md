# 百度地图加载问题

#### 问题
用create-creat-app生成的代码中，在index.html中引入baidu map：http://api.map.baidu.com/getscript?v=2.0&ak=iVuZxPQ8Ub2Oqc24fGLUsLEOTVUonY, 出现问题 chrome不显示百度地图，并且提示错误：A Parser-blocking, cross-origin script, is invoked via document.write. 
#### 原因
百度地图加载有个中间步骤，生成一个新的url，中间使用了document.write方法；而chrome渲染后不允许write方法
#### 解决方案
把引入的url改成如下形式:
  src="http://api.map.baidu.com/getscript?v=2.0&ak=iVuZxPQ8Ub2Oqc24fGLUsLEOTVUonY1d&services=&t=20170725120922">


