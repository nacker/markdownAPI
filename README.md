# 接口文档示例
|  类型  |服务器地址|
|------ |----- |
| <font color=red>Test    | http://xxx.xxx.xxx:xxx
| <font color=red>Develop | http://xxx.xxx.xxx:xxx
| <font color=red>Product | http://xxx.xxx.xxx:xxx

 ## 用户模块

|  接口  |请求方式| 说明 |
|------ |----- |----- |
|[/user](#postuser) | POST | 用户登录|
|[/user](#getuser) | GET | 获取用户详情|


## 接口详情

* <span id = "postuser">登录接口</span>

    * 接口地址：/user

    * 返回格式：Json

    * 请求方式：Post

    * 请求示例：/user

    * 接口备注：用户登录。

    * 请求参数说明：

        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        |<font color=red>username | string |true|用户名|
        |<font color=red>password | string |true|用户密码|
        
        
    * JSON请求示例：

             "Header":{
                 "token": "",
             }
              "Body":{
                 "username": "",
                 "password": "",
             }  
        

    * 返回参数说明：

        | 名称 | 类型 |说明|
        |----- |------|----|
        | code | int| 状态码
        | data | object|具体数据|
        | token | string|登录方式|

    * JSON返回示例：

             {
                 "code": 200,
                 "data": {
                     "token": "1234567890",
                 }
             }


---

* <span id = "getuser">获取用户详情</span>

    * 接口地址：/user

    * 返回格式：Json

    * 请求方式：Post

    * 请求示例：/user

    * 接口备注：通过用户信息，请求获得全局策略。

    * 请求参数说明：

        | 名称 | 类型 | 必填 |说明|
        |----- |------| ---- |----|
        | Header ||true|请求报文头|
        | token | string |true|用户登录后token，没有登录则为空字符串|
        |------|------|-----|------|
        |<font color=red> username | string |true|用户名|
        |<font color=red> password | string |true|用户密码|

    * 返回参数说明：

        | 名称 | 类型 |说明|
        |----- |------|----|
        | code    | int   | 状态码|
        |data     | object|具体数据|
        |username | string|用户名|
        |phone    | string|手机号|
        |sex		 |	int   |性别：0-未知、1-男、2-女|

    * JSON返回示例：

             {
                 "code": 200,
                 "data": {
                     "username": "1234567890",
                     "phone": "1234567890",
                     "Sex":1,
                 }
             }


---

## 响应码说明
响应码	|说明  
:----	|:---
200		|处理成功
301		|解析报文错误
302		|无效调用凭证
303		|参数不正确
500		|系统内部错误
999		|处理失败

