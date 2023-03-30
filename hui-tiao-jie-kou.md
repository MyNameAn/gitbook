# 😄 回调接口

​ 2.1）商户交易通知

> 商户交易成功后，推送交易记录。

#### 请求参数

| 字段             | 类型         | 描述                                                                                           |
| -------------- | ---------- | -------------------------------------------------------------------------------------------- |
| agentOrderId   | String     | 订单号                                                                                          |
| agentNo        | String     | 交易机具代理商号                                                                                     |
| agentName      | String     | 交易机具代理姓名                                                                                     |
| posProductId   | Long       | 对应产品id                                                                                       |
| posProductName | String     | 产品名字                                                                                         |
| finishDate     | String     | 交易时间                                                                                         |
| posTradeType   | String     | 交易方式，POS\_CREDIT：贷记卡，POS\_DEBIT：借记卡，POS\_FLASH：云闪付，WXPAY：微信，ALIPAY：支付宝，UNIONPAY：银联，VIP：享惠收款。 |
| memberNo       | String     | 商户编号                                                                                         |
| realName       | String     | 商户名                                                                                          |
| phoneNoTemp    | String     | 商户手机号（脱敏）                                                                                    |
| orderAmount    | BigDecimal | 订单金额                                                                                         |
| snno           | String     | 设备号（FD开头）                                                                                    |
| tusn           | String     | 厂商tusn码                                                                                      |
| orderStatus    | String     | 订单状态                                                                                         |
| bankName       | String     | 银行名称                                                                                         |
| brandType      | String     | 厂商名称                                                                                         |
| modelType      | String     | 设备类型                                                                                         |
| firstPay       | String     | 是否激活交易，1:是，0:否，对于有服务费机器为首笔服务费交易，也就是交了首笔服务费的订单，对于无服务费机器，为满达标激活条件的那笔交易                         |
| memberFee      | BigDecimal | 总手续费，例如3.2元                                                                                  |
| memberFeeRate  | BigDecimal | 商户费率，例如0.0055                                                                                |
| debitTopRate   | BigDecimal | 商户借记卡封顶费率，例如30元                                                                              |
| d0IncreaseRate | BigDecimal | 借记卡D0加收费率，例如0.0002                                                                           |
| manaRate1      | BigDecimal | 商户管理费1费率，例如0.0003                                                                            |
| manaRate2      | BigDecimal | 商户管理费2费率，例如0.0002                                                                            |
| singleFee      | BigDecimal | 收取商户的流量卡服务费，如：36、50、48、60等，未收取订单推送0                                                          |
| simFee         | BigDecimal | 收取商户的安心服务费，未收取订单推送0                                                                          |
| reasServeFee   | BigDecimal | 收取商户的安心服务费，未收取订单推送0                                                                          |

### 2.2）商户费率变更通知

> 商户费率变更通知后，推送该变更记录相关信息；部分字段无值时候，不返回该字段内容，请注意。

#### 请求参数

| 字段                 | 类型         | 描述                               |
| ------------------ | ---------- | -------------------------------- |
| agentNo            | String     | 代理商号                             |
| agentName          | String     | 代理姓名                             |
| memberNo           | String     | 商户编号                             |
| realName           | String     | 商户名称                             |
| phoneNoTemp        | String     | 注册手机号（脱敏）                        |
| tusn               | String     | 厂商tusn码                          |
| snNo               | String     | 设备号                              |
| creditRadio        | BigDecimal | 贷记卡费率                            |
| creditWithdrawType | String     | 贷记卡结算方式（枚举：T1、D0）其余结算方式参考这里      |
| debitRadio         | BigDecimal | 借记卡费率                            |
| debitWithdrawType  | String     | 借记卡结算方式（参考上面结算方式枚举值）             |
| flashRadio         | BigDecimal | 云闪付费率                            |
| flashWithdrawType  | String     | 云闪付结算方式（参考上面结算方式枚举值）             |
| vipRadio           | BigDecimal | 享惠收款费率                           |
| vipWithdrawType    | String     | 享惠收款结算方式（参考上面结算方式枚举值）            |
| wxpayRadio         | BigDecimal | 扫码费率                             |
| wxWithdrawType     | String     | 扫码结算方式（参考上面结算方式枚举值）              |
| finshDate          | String     | 本次业务的完成时间参考值：yyyy-MM-dd HH:mm:ss |

### 2.3）商户注册通知

> 商户注册后，推送相关信息。

#### 业务参数

| 字段          | 类型     | 描述      |
| ----------- | ------ | ------- |
| agentNo     | String | 代理商号    |
| agentName   | String | 代理姓名    |
| tusn        | String | 厂商tusn码 |
| snNo        | String | 设备号     |
| productName | String | 产品名称    |
| phoneNo     | String | 手机号（脱敏） |
| memberNo    | String | 商户编号    |

### 2.4）终端绑定、解绑通知

> 商户终端绑定、解绑后，推送该变终端绑定相关信息。

#### 业务参数

| 字段             | 类型     | 描述                               |
| -------------- | ------ | -------------------------------- |
| agentNo        | String | 代理商号                             |
| agentName      | String | 代理姓名                             |
| memberNo       | String | 商户编号                             |
| tusn           | String | 厂商tusn码                          |
| snNo           | String | 设备号                              |
| productName    | String | 产品名称                             |
| bindTermStatus | String | 类型（绑定、解绑）BINDMER ：绑定UNBINDMER：解绑 |
| finshDate      | String | 本次业务的完成时间参考值：yyyy-MM-dd HH:mm:ss |

### 2.5）商户实名认证通知

> 商户实名认证后，推送相关信息。

#### 业务参数

| 字段           | 类型     | 描述                      |
| ------------ | ------ | ----------------------- |
| agentNo      | String | 代理商编号                   |
| memberNo     | String | 商户编号                    |
| memberName   | String | 名称                      |
| phoneNo      | String | 手机号（脱敏）                 |
| idCardNo     | String | 证件号（脱敏）                 |
| memberStatus | String | 状态：ACTIVE：成功INACTIVE：失败 |
| finshDate    | String | 业务完成时间                  |

### 2.6）商户结算通知

> 商户提现以后，推送相关信息；部分字段无值时候，不返回该字段内容，请注意。

#### 业务参数

| 字段              | 类型         | 描述                                                                                                           |
| --------------- | ---------- | ------------------------------------------------------------------------------------------------------------ |
| agentNo         | String     | 代理商编号                                                                                                        |
| agentName       | String     | 代理商名称                                                                                                        |
| orderNum        | String     | 结算订单号                                                                                                        |
| trxOrderNo      | String     | 交易订单号                                                                                                        |
| mergeTrxOrderNo | String     | T1结算单号，无值时候不返回                                                                                               |
| memberNo        | String     | 商户编号                                                                                                         |
| memberName      | String     | 商户名称                                                                                                         |
| phoneNo         | String     | 手机号                                                                                                          |
| orderAmount     | BigDecimal | 交易金额                                                                                                         |
| realAmount      | BigDecimal | 到账金额                                                                                                         |
| cardNo          | String     | 结算账户                                                                                                         |
| orderStatus     | String     | 状态INIT:待处理SUCCESS:提现成功FAILED:提现失败DOING:银行处理中DEBITCOMPLETE:系统处理中RISK\_AUTH\_HANG:风控认证挂起RISK\_SYS\_HANG:风控系统挂起 |
| completeDate    | String     | 出款时间                                                                                                         |
| retMsg          | String     | 返回信息                                                                                                         |
