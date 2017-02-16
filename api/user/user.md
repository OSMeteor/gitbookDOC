#####  /user/

* [^login]:   
* [^register]:  

[^login] 

---
 
     Name   :login
     Method :POST	
     Url    : /g/user/login
######Request
| Parameters | type      | required  |  Remarks          |
| ---------- |:---------:| -----:  |----------------:  
|access_token,token,authorization|string|Y| body or header from /auth/getAccessToken |
|username|string|Y| email or phone number |
|password|string|Y| md5(password) | 
######Respose
| status | msg      | Remarks  |      result      |
| ---------- |:---------:| -----:  |----------------:
| 200 |success   |登陆成功       |   |
| 300 |get token error | get token from redis err  |    |
| 301 |system error | find db for email |    |
| 302 |system error | find db for mobile |    |
| 304 |system error | save  user to DB error |    | 



     	Example： /g/user/login
 
```javascript
data eg:
 { status: 200,
  msg: 'success',
  result: 
   {  }
```

---

[^register]

---

     Name   :register
     Method :POST
     Url    : /g/user/register
######Request
| Parameters | type      | required  |  Remarks          |
| ---------- |:---------:| -----:  |----------------:
|access_token,token,authorization|string|Y| body or header from auth |
|username|string|Y| email or phone number |
|password|string|Y| md5(password) | 
|vcode|string|N| 验证码手机号注册必填 |
######Respose
| status | msg      | Remarks  |      result      |
| ---------- |:---------:| -----:  |----------------:
|access_token,token,authorization|string|Y| body or header from  auth |
| 200 |success   |注册成功       |   |
| 300 |get token error | get token from redis err  |    | 
| 403 |param not valid |username is required       |    |
| 404 |param not valid |password is required      |    |
| 405 |param not valid |password vierify Error      |    |

     	Example： /g/user/register

```javascript
 { status: 200,
  msg: 'success',
  result: 
   {   }
```

---

