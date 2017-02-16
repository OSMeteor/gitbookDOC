#####  错误码说明

---
 
     -1  服务器繁忙（CPU  内存）
    500  request error or params error
	503  no supper this dev input
	200-300  成功 normal
   	规定以1 0 开头的提示都是监控程序所用的错误
   	以 2 6 开头的提示都是成功
   	以 3 7 开头的都是db这类的交互错误
   	以 4 8 开头的都是提示给用户看的
   	以 5 9 开头的都是 服务器内部错误（比如连接不上mongodb）服务器CPU 内存
   
	eg:
	20000  60000 normal
	30000  70000 prompt 业务中的逻辑错误比如 redis mongodb 错误
	40000  80000 prompt 用户输入错误(需要提示给用户) 对外的
	50000  90000 system 服务器内部错误 （内部日志记录）
	
---

#####  登录验证token说明

	/p 的api 	不需要传入 userid 需传入access_token,token,authorization（body,header query ）
	/g 的api	需传 guest  access_token  /p 的都需要替换登录之后的 token 
