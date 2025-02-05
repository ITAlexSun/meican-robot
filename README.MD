# 美餐订餐机器人

## 功能

+ 订餐提醒（短信+微信）
+ 自动下单
+ 支持多用户
+ 支持用户自定义订餐时间与地点
+ 自动下单支持多种餐品选择策略（下单次数最多、最近一次下单、距离优先等）

### 每日提醒：

1. 机器人会在每次截止订餐前30分钟发送提醒短信，提醒用户下单。
2. 订餐时间截止前10分钟再次检测，如果用户仍未下单，并且用户开启了自动下单功能，则根据用户配置的餐品选择策略自动下单。

### 每周提醒：

1. 每周六检测下周可以订的午餐，有可以订的餐时发送提醒。

### 使用方法

目前仅实现了一个新增接口

POST /user 添加用户

|  参数   | 含义  |
|  ----  | ----  |
| username  | 邮箱 |
| password  | 美餐登录密码（可选）|
| cookies  | 美餐cookies（和密码二选一） |
| phone  | 接收短信的手机号|
| corpName  | 取餐地点|
| strategy  | 餐品选择策略|
| checkLunch  | 发送午餐提醒|
| autoLunch  | 午餐自动下单|
| checkDinner  | 发送晚餐提醒|
| autoDinner  | 晚餐自动下单|

cookies获取方式:
登录网页版美餐随意发个请求，将header中的cookies完整复制即可

 