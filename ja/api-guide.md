
## CloudTrail > APIガイド

> Cloud TrailにRestful APIを呼び出し、ユーザーが設定した条件に合うイベントを照会できます。

## URL & Appkey
RESTful APIを使用するにはAppKeyが必要です。
[CONSOLE]の右上で、発行されたKey情報を確認できます。
![[図1] AppKey & SecretKey確認](http://static.toastoven.net/prod_cloudtrail/cloudtrail_20190924.png)
<center>[図1] AppKey & SecretKey確認</center>
## RESTful APIガイド

### Common Response Body

すべてのAPIリクエストに対して、HTTPレスポンスコードは200でレスポンスする。
詳細なレスポンス結果は、Response Bodyのheader項目を参照する。

```json
{
	"header" : {
		"isSuccessful" : true,
		"resultCode": 0,
		"resultMessage" : "Success."
	}
}
```

|Key|	Type|	Description|
|---|---|---|
|header|	Object|	レスポンスヘッダ|
|header.isSuccessful|	boolean|	成否|
|header.resultCode|	int|	レスポンスコード。成功時は0、失敗時はエラーコードを返す|
|header.resultMessage|	String|	レスポンスメッセージ。成功時は「SUCCESS」、失敗時はエラーメッセージを返す|

### 1. Event照会
* 発生したEventの照会を行います。
* Eventの照会時、ユーザーが設定した検索条件により結果が照会されます。
* RequestBodyにこの検索条件を含める必要があります。

**[Method, URL]**

|Method|	URI|
|---|---|
|POST|	/cloud-trail/v1.0/appkeys/{appKey}/events/search|

**[Path Variable]**

|Key|	Value|
|---|---|
|appKey|	[CONSOLE]で発行されたAppKey|

**[Request Body]**

```json
{
    "idNo" : "string",
    "eventId" : "string",
    "startDate": "2019-09-01T02:00:00.000Z",
    "endDate": "2019-09-12T03:13:00.000Z",
    "page": {
       "sortBy": "string",
       "limit": 20,
       "page": 0
    }
} 
```

| Key | Type | Required  | Description |
| --- | --- | --- | --- |
| idNo | String | X | Eventを発生させた会員IdNo (uuid) |
| eventId | String | O | 照会するEventのID |
| startDate | Date | O | 照会する期間の開始日 |
| endDate | Date |O  | 照会する期間の終了日 |
| page | Object | O | 照会結果のPage条件 |
| page.sortBy | String | X | 照会結果のサイズソート条件 |
| page.limit | Integer | O | 照会結果のサイズ条件 |
| page.page | Integer | O | 照会結果のPageのうち、照会したいPage条件 |


**[Response Body]**
```json
{
    "header": {
        "resultCode": 0,
        "resultMessage": "SUCCESS",
        "isSuccessful": true
    },
    "page": {
        "content": [
            {
                "eventTime": "2019-09-04T10:31:49.348+0000",
                "userIdNo": "24bfb870-46da-11e9-aafd-005056ac7022",
                "userIp":"10.162.5.18",
                "userAgent":"ReactorNetty/0.8.4.RELEASE",
                "userName": "山田太郎",
                "userId": "test_email@nhn.com",
                "eventSourceType": "API",
                "productId": "M0XnzOFE",
                "region": "string",
                "orgId": "Y4PbNFUlBsRgAxcU",
                "projectId": "string",
                "projectName": "string",
                "appKey": "string",
                "tenantId": "string",
                "eventId": "event_id.iam.member.role.update",
                "request": "{\n\t\"id\" : \"2\",\n\t\"productId\" : \"M0XnzOFE\",\n\t\"uuid\" : \"24bfb870-46da-11e9-aafd-005056ac7022\"\n\t\n}",
                "response": "{\"header\":{\"resultCode\":0,\"resultMessage\":\"SUCCESS\",\"isSuccessful\":true}}",
                "eventTarget": {
                    "targetMembers": [
                        {
                            "idNo": "9c30dff8-53ba-4f18-8b44-22ab3b1678d7",
                            "name": "林巨正",
                            "userCode": "test_user",
                            "emailAddress": "test_email2@nhn.com"
                        }
                    ]
                }
            },
        ],
        "pageable": "INSTANCE",
        "totalPages": 1,
        "totalElements": 1,
        "last": true,
        "size": 0,
        "number": 0,
        "numberOfElements": 1,
        "first": true,
        "sort": {
            "sorted": false,
            "unsorted": true,
            "empty": true
        },
        "empty": false
    }
}
```