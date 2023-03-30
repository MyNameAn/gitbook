---
coverY: 0
---

# 😌 对接说明

1. 服务商对接接口前与我方技术人员沟通，获取密钥secret，用于后期接收到数据后做签名校验
2. 服务商对接前，需要提供回调地址url，请求类型为POST ，接收参数为JSON格式的字符串
3. 服务商接收到回调字符串后，先对内容进行验签操作
4. 验签通过后，根据业务类型method处理业务逻辑
5. 获取data数据即为业务所需参数

### 回调数据格式

```
{
    "method":"CHANGETRMBIND",
    "agentNo":"8010041010041",
    "data":{
        "agentNo":"8010041010041",
f43a2"
}
```

* method （回调业务类型）
  * TRADE 商户交易通知
  * CHANGERATE 商户费率变更通知
  * CHANGETRMBIND 终端绑定、解绑通知
  * REGISTER 商户注册通知
  * MERCHANTAUTH 商户实名认证通知
  * MERCHANTSETTLEMENT 商户结算通知
* agentNo （代理商编号）
* data （业务数据，基于该数据验证签名或处理自己的业务）
* sign （签名）
  * 下方有对签名sign的单独描述

### 签名Sign

服务商接收到回调数据后，需要对数据进行验签，具体验签规则如下：

1. 服务商对接收到的数据进行处理，获得data内的数据
2. 对data内的数据 按key做升序排列
3. 把排列后的数

\
