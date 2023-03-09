# APISpace 介绍
**本 API 服务由 [APISpace（apispace.com）](https://www.apispace.com/?utm_source=github&utm_term=yinhangkaocr) 提供。**

APISpace 是 Eolink 旗下专业的 API 开放与交易平台，为广大企业以及个人开发者提供多维度、全方位的API接口，覆盖短信验证、天气查询、快递物流、OCR文字识别等海量 API 服务，帮助用户快速获取数据，降低获取数据的成本和难度，提升开发效率。

APISpace 提供15种开发语言的代码示例，分别是：
- Java(OK HTTP)
- HTTP
- cURL
- 微信小程序
- PHP(pecl_http)、PHP(cURL)
- Python(http.client)、Python(Requests)
- JavaScript(Jquery AJAX)、JavaScript(XHR)
- NodeJS(Native)、NodeJS(Request)
- Ruby(Net:Http)
- Shell(Httpie)、Shell(cUrl)

# 银行卡识别OCR
结构化识别多款主流银行卡的卡号、有效期、发卡行、卡片类型、持卡人5个关键字段，识别准确率超过99%。

**使用该产品前，您需要通过 [https://www.apispace.com/eolink/api/bankcard/introduction](https://www.apispace.com/eolink/api/bankcard/introduction?utm_source=github&utm_term=yinhangkaocr) 申请API服务**

本文档末尾提供了 Python(Requests) 的调用代码示例，可以前往文档末尾查看。

更多代码示例：[https://www.apispace.com/eolink/api/bankcard/guidence/](https://www.apispace.com/eolink/api/bankcard/guidence/?utm_source=github&utm_term=yinhangkaocr)

### 识别效果

示例图片：

![image](https://user-images.githubusercontent.com/36323798/223986410-e69526ea-f475-4962-b0fa-bf92d41ff9c0.png)


返回结果：

```
{
    "result": {
        "number": "6259650891116660",
        "date": ["02/25"],
        "bank": "中国建设银行",
        "type": "信用卡",
        "UnionPay": true,
        "VISA": false,
        "MasterCard": false
    },
    "log_id": "5f5f2132-bda4-11ed-aa4b-000000011457"
}
```


### 应用场景

1.  #### 电商支付绑卡

接入银行卡识别API服务实现拍照识别，结构化返回卡号、卡片类型等信息，有效提升信息录入的准确性，并降低用户手工输入成本，提升用户使用体验。


2.  #### 金融远程身份认证

结构化识别录入客户银行账户和身份信息，可应用于金融场景用户实名认证，有效降低用户输入成本，提升用户体验。


### 服务保障
![image](https://user-images.githubusercontent.com/36323798/223986464-c81ded9f-50e5-4d4b-b79e-878440b518db.png)

### Python(Requests) 调用代码示例

```
import requests

url = "https://eolink.o.apispace.com/bankcard/bankcard"

payload = {"image":"","url":"https://data.eolinker.com/course/Wp8wCVb9fdba886ac50f5805efd4b88de9ddb0ab1b23ac0"}

headers = {
    "X-APISpace-Token":"",
    "Authorization-Type":"apikey",
    "Content-Type":"application/json"
}

response=requests.request("POST", url, data=json.dumps(payload), headers=headers)

print(response.text)

```
