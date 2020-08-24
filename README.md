## 网关地址

测试环境：http://219.153.49.186:81/

---

## 登录接口

**接口地址** `/user/loginWeb/login`


**请求方式** `POST`


**consumes** `["application/json"]`


**produces** `["*/*"]`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
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

---

## 刷新token

**接口地址** `/user/loginWeb/refreshToken`


**请求方式** `POST`


**consumes** `["application/json"]`


**produces** `["*/*"]`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| refreshToken         |      刷新token   |     query        |       true      | string   |      |
            




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

---

## 获取当前用户信息

**接口地址** `/user/userWeb/getCurrentUser`


**请求方式** `GET`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| access_token         |      请求的token参数   |     query        |       false      | string   |      |
            




**响应状态**

| 状态码         | 说明                             |    schema                         |
| ------------ | -------------------------------- |---------------------- |
| 200         | OK                        |HttpResult«用户信息»                          |
| 401         | Unauthorized                        |                          |
| 403         | Forbidden                        |                          |
| 404         | Not Found                        |                          |




**响应参数**

| 参数名称         | 说明                             |    类型 |  schema |
| ------------ | -------------------|-------|----------- |
| error     |错误消息      |    string   |       |
| errorCode     |错误码      |    string   |       |
| result     |返回结果      |    用户信息   |   用户信息    |
| success     |是否成功      |    boolean   |       |
| timestamp     |响应时间      |    integer(int64)   |   integer(int64)    |
            



**schema属性说明**
  
**用户信息**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| aliPayAccount         |     支付宝账号      |  string   |      |
| aliPayRealName         |     支付宝真实姓名      |  string   |      |
| createTime         |     创建时间      |  string(date-time)   |      |
| enable         |     是否可用      |  boolean   |      |
| id         |           |  integer(int64)   |      |
| phone         |     手机号      |  string   |      |
| qq         |     qq号      |  string   |      |
| updateTime         |     更新时间      |  string(date-time)   |      |
| username         |     用户名      |  string   |      |
            




**响应示例**


```json
{
	"error": "",
	"errorCode": "",
	"result": {
		"aliPayAccount": "",
		"aliPayRealName": "",
		"createTime": "",
		"enable": true,
		"id": 0,
		"phone": "",
		"qq": "",
		"updateTime": "",
		"username": ""
	},
	"success": true,
	"timestamp": 0
}
```

---

## 获取项目选项列表

**接口地址** `/user/codeWeb/getProjectSelects`


**请求方式** `GET`


**consumes** ``


**produces** `["*/*"]`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| access_token         |      请求的token参数   |     query        |       true      | string   |      |
| keyword         |      查询关键字   |     query        |       false      | string   |      |
| pageNumber         |      当前页，从1开始   |     query        |       false      | integer   |      |
| pageSize         |      每页条数   |     query        |       false      | integer   |      |






**响应状态**

| 状态码         | 说明                             |    schema                         |
| ------------ | -------------------------------- |---------------------- |
| 200         | OK                        |HttpResult«PageResult«ProjectSelectVO»»                          |
| 401         | Unauthorized                        |                          |
| 403         | Forbidden                        |                          |
| 404         | Not Found                        |                          |




**响应参数**

| 参数名称         | 说明                             |    类型 |  schema |
| ------------ | -------------------|-------|----------- |
| error     |错误消息      |    string   |       |
| errorCode     |错误码      |    string   |       |
| result     |返回结果      |    PageResult«ProjectSelectVO»   |   PageResult«ProjectSelectVO»    |
| success     |是否成功      |    boolean   |       |
| timestamp     |响应时间      |    integer(int64)   |   integer(int64)    |
            



**schema属性说明**
  
**PageResult«ProjectSelectVO»**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| list         |     当页数据      |  array   | ProjectSelectVO     |
| page         |     分页信息      |  PageInfo   | PageInfo     |
            

**ProjectSelectVO**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| id         |     项目ID      |  integer(int64)   |      |
| projectKeyword         |     项目关键词      |  string   |      |
| projectName         |     项目名      |  string   |      |
| recognitionSoundPrice         |     识别语音单价      |  number   |      |
| smsPrice         |     接收短信单价      |  number   |      |
| sound         |     能否接收语音      |  boolean   |      |
| soundPrice         |     接收语音单价      |  number   |      |
| wholesalePrice         |     批发价      |  number   |      |
            

**PageInfo**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| pageNumber         |     页码      |  integer(int32)   |      |
| pageSize         |     每页数量      |  integer(int32)   |      |
| totalElements         |     总数据量      |  integer(int64)   |      |
| totalPages         |     总页数      |  integer(int32)   |      |
            




**响应示例**


```json
{
	"error": "",
	"errorCode": "",
	"result": {
		"list": [
			{
				"id": 0,
				"projectKeyword": "",
				"projectName": "",
				"recognitionSoundPrice": 0,
				"smsPrice": 0,
				"sound": true,
				"soundPrice": 0,
				"wholesalePrice": 0
			}
		],
		"page": {
			"pageNumber": 0,
			"pageSize": 0,
			"totalElements": 0,
			"totalPages": 0
		}
	},
	"success": true,
	"timestamp": 0
}
```

---

## 获取卡商选项列表

**接口地址** `/user/codeWeb/getMerchantSelects`


**请求方式** `GET`


**consumes** ``


**produces** `["*/*"]`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| access_token         |      请求的token参数   |     query        |       true      | string   |      |
| merchantName         |      卡商名   |     query        |       false      | string   |      |
| pageNumber         |      当前页，从1开始   |     query        |       false      | integer   |      |
| pageSize         |      每页条数   |     query        |       false      | integer   |      |
| projectId         |      专属项目id   |     query        |       false      | integer   |      |






**响应状态**

| 状态码         | 说明                             |    schema                         |
| ------------ | -------------------------------- |---------------------- |
| 200         | OK                        |HttpResult«PageResult«MerchantSelectVO»»                          |
| 401         | Unauthorized                        |                          |
| 403         | Forbidden                        |                          |
| 404         | Not Found                        |                          |




**响应参数**

| 参数名称         | 说明                             |    类型 |  schema |
| ------------ | -------------------|-------|----------- |
| error     |错误消息      |    string   |       |
| errorCode     |错误码      |    string   |       |
| result     |返回结果      |    PageResult«MerchantSelectVO»   |   PageResult«MerchantSelectVO»    |
| success     |是否成功      |    boolean   |       |
| timestamp     |响应时间      |    integer(int64)   |   integer(int64)    |




**schema属性说明**
  
**PageResult«MerchantSelectVO»**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| list         |     当页数据      |  array   | MerchantSelectVO     |
| page         |     分页信息      |  PageInfo   | PageInfo     |
            

**MerchantSelectVO**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| id         |     卡商id      |  integer(int64)   |      |
| username         |     用户名      |  string   |      |
            

**PageInfo**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| pageNumber         |     页码      |  integer(int32)   |      |
| pageSize         |     每页数量      |  integer(int32)   |      |
| totalElements         |     总数据量      |  integer(int64)   |      |
| totalPages         |     总页数      |  integer(int32)   |      |





**响应示例**


```json
{
	"error": "",
	"errorCode": "",
	"result": {
		"list": [
			{
				"id": 0,
				"username": ""
			}
		],
		"page": {
			"pageNumber": 0,
			"pageSize": 0,
			"totalElements": 0,
			"totalPages": 0
		}
	},
	"success": true,
	"timestamp": 0
}
```

---

## 获取运营商列表

**接口地址** `/user/codeWeb/getOperators`


**请求方式** `GET`


**consumes** ``


**produces** `["*/*"]`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| access_token         |      请求的token参数   |     query        |       true      | string   |      |
            





**响应状态**

| 状态码         | 说明                             |    schema                         |
| ------------ | -------------------------------- |---------------------- |
| 200         | OK                        |HttpResult«List«OperatorVO»»                          |
| 401         | Unauthorized                        |                          |
| 403         | Forbidden                        |                          |
| 404         | Not Found                        |                          |




**响应参数**

| 参数名称         | 说明                             |    类型 |  schema |
| ------------ | -------------------|-------|----------- |
| error     |错误消息      |    string   |       |
| errorCode     |错误码      |    string   |       |
| result     |返回结果      |    array   |   OperatorVO    |
| success     |是否成功      |    boolean   |       |
| timestamp     |响应时间      |    integer(int64)   |   integer(int64)    |
            



**schema属性说明**
  
**OperatorVO**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| desc         |     运营商描述      |  string   |      |
| name         |     运营商枚举名      |  string   |      |
            




**响应示例**


```json
{
	"error": "",
	"errorCode": "",
	"result": [
		{
			"desc": "",
			"name": ""
		}
	],
	"success": true,
	"timestamp": 0
}
```

---

## 批量获取手机号

**接口地址** `/user/codeWeb/getPhones`


**请求方式** `GET`


**consumes** ``


**produces** `["*/*"]`


**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| access_token         |      请求的token参数   |     query        |       true      | string   |      |
| area         |      地区   |     query        |       false      | string   |      |
| merchantUid         |      卡商id   |     query        |       false      | integer   |      |
| num         |      获取数量   |     query        |       true      | string   |      |
| operator         |      运营商,可用值:CHINA_TELECOM,CHINA_MOBILE,CHINA_UNICOM   |     query        |       false      | string   |      |
| phone         |      手机号（设置该值时，运营商、地区、卡商选项无效）   |     query        |       false      | string   |      |
| phoneService         |      服务类型,可用值:SMS,SOUND,SMS_AND_SOUND   |     query        |       true      | string   |      |
| projectId         |      项目id   |     query        |       true      | integer   |      |
            





**响应状态**

| 状态码         | 说明                             |    schema                         |
| ------------ | -------------------------------- |---------------------- |
| 200         | OK                        |HttpResult«List«PhoneVO»»                          |
| 401         | Unauthorized                        |                          |
| 403         | Forbidden                        |                          |
| 404         | Not Found                        |                          |




**响应参数**

| 参数名称         | 说明                             |    类型 |  schema |
| ------------ | -------------------|-------|----------- |
| error     |错误消息      |    string   |       |
| errorCode     |错误码      |    string   |       |
| result     |返回结果      |    array   |   PhoneVO    |
| success     |是否成功      |    boolean   |       |
| timestamp     |响应时间      |    integer(int64)   |   integer(int64)    |
            



**schema属性说明**
  
**PhoneVO**

| 属性名称         |  说明          |   类型  |  schema |
| ------------ | ------------------|--------|----------- |
| area         |     归属地      |  string   |      |
| merchantUid         |     卡商id      |  integer(int64)   |      |
| operator         |     运营商,可用值:CHINA_TELECOM,CHINA_MOBILE,CHINA_UNICOM      |  string   |      |
| operatorDesc         |     运营商描述      |  string   |      |
| phone         |     手机号      |  string   |      |
            




**响应示例**


```json
{
	"error": "",
	"errorCode": "",
	"result": [
		{
			"area": "",
			"merchantUid": 0,
			"operator": "",
			"operatorDesc": "",
			"phone": ""
		}
	],
	"success": true,
	"timestamp": 0
}
```

---

## 释放当前获取的全部手机号

**接口地址** `/user/codeWeb/unlockPhone`


**请求方式** `GET`


**consumes** ``


**produces** `["*/*"]`


**接口描述** ``

**请求参数**

| 参数名称         | 说明     |     参数类型 |  是否必须      |  类型   |  schema  |
| ------------ | -------------------------------- |-----------|--------|----|--- |
| access_token         |      请求的token参数   |     query        |       true      | string   |      |
            





**响应状态**

| 状态码         | 说明                             |    schema                         |
| ------------ | -------------------------------- |---------------------- |
| 200         | OK                        |HttpResult                          |
| 401         | Unauthorized                        |                          |
| 403         | Forbidden                        |                          |
| 404         | Not Found                        |                          |




**响应参数**

| 参数名称         | 说明                             |    类型 |  schema |
| ------------ | -------------------|-------|----------- |
| error     |错误消息      |    string   |       |
| errorCode     |错误码      |    string   |       |
| result     |返回结果      |    object   |       |
| success     |是否成功      |    boolean   |       |
| timestamp     |响应时间      |    integer(int64)   |   integer(int64)    |
            




**响应示例**


```json
{
	"error": "",
	"errorCode": "",
	"result": {},
	"success": true,
	"timestamp": 0
}
```

---

## 通过WebSocket接收短信

### 连接地址

测试环境：ws://219.153.49.186:10028

### 连接方式

ws://{ip}:{port}?id=${用户id}&access_token=${accessToken}

### 说明

连接成功后，需要间隔十分钟以内向服务端发送心跳，心跳格式：{"action":"PING"}，服务端响应心跳：{"action":"PING","response":"PONE"}

### 接收短信

如果当前用户获取到的号码收到指定项目的短信，则服务端会发送如下格式的数据包给客户端

```json
{
	"action": "SMS",
	"response": {
		"content": "【淘宝网】您于2020年08月24日申请了手机号码注册，校验码是224679",
		"downloadUrl": null,
		"phone": "13594479413"
	}
}
```

#### 参数说明

action：SMS-短信，SOUND-语音  

response：响应参数  

response.content：短信正文，如果是语音则为语音转换的文本   

response.phone：收信号码   

response.downloadUrl：如果时语音，这个参数才有值，值为语音文件的下载地址





