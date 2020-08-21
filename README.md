## 登录

**接口地址** `/user/loginWeb/login`


**请求方式** `POST`


**consumes** `["application/json"]`


**produces** `["*/*"]`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| access_token         |      请求的token参数   |     query        |       false      | string   |      |
| password         |      登录密码   |     query        |       true      | string   |      |
| username         |      用户名   |     query        |       true      | string   |      |
            

**响应状态**

| 状态码         | 说明                             |    schema                         |
| ------------ | -------------------------------- |---------------------- |
| 200         | OK                        |HttpResult«TokenVO»                          |
| 201         | Created                        |                          |
| 401         | Unauthorized                        |                          |
| 403         | Forbidden                        |                          |
| 404         | Not Found                        |                          |




**响应参数**

| 参数名称         | 说明                             |    类型 |  schema |
| ------------ | -------------------|-------|----------- |
| error     |错误消息      |    string   |       |
| errorCode     |错误码      |    string   |       |
| result     |返回结果      |    TokenVO   |   TokenVO    |
| success     |是否成功      |    boolean   |       |
| timestamp     |响应时间      |    integer(int64)   |   integer(int64)    |
            



**schema属性说明**
  
**TokenVO**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| accessToken         |     token      |  string   |      |
| accessTokenExpiration         |     token过期时间(秒)      |  integer(int64)   |      |
| refreshToken         |     刷新token      |  string   |      |
| refreshTokenExpiration         |     刷新token过期时间(秒)      |  integer(int64)   |      |
            




**响应示例**


```json
{
	"error": "",
	"errorCode": "",
	"result": {
		"accessToken": "",
		"accessTokenExpiration": 0,
		"refreshToken": "",
		"refreshTokenExpiration": 0
	},
	"success": true,
	"timestamp": 0
}
```


