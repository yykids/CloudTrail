   
## CloudTrail > API 가이드

> Cloud Trail에 Restful API를 호출해, 사용자가 설정한 조건에 맞는 이벤트를 조회할 수 있다.

## URL & Appkey
RESTFUL API를 사용하려면 AppKey가 필요하다.
[CONSOLE] 의 우측 상단에서 발급된 Key 정보를 확인 할 수 있다.
![[그림 1] AppKey & SecretKey 확인](http://static.toastoven.net/prod_cloudtrail/cloudtrail_20190924.png)
<center>[그림 1] AppKey & SecretKey 확인</center>
## RESTFUL API 가이드

### Common Response Body

모든 API 요청에 대해 HTTP 응답 코드는 200 으로 응답한다.
자세한 응답 결과는 Response Body 의 header 항목을 참고한다.

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
|header|	Object|	응답헤더|
|header.isSuccessful|	boolean|	성공 여부|
|header.resultCode|	int|	응답 코드. 성공 시 0, 실패 시 에러코드 반환|
|header.resultMessage|	String|	응답 메시지. 성공 시 "SUCCESS", 실패 시 에러메시지 반환|

### 1. Event 조회
* 발생한 Event 에 대해서 조회를 합니다. 
* Event 조회 시, 사용자가 설정한 검색 조건에 의해 결과가 조회됩니다.
* RequestBody에 이 검색 조건을 포함해야 합니다.

**[Method, URL]**

|Method|	URI|
|---|---|
|POST|	/cloud-trail/v1.0/appkeys/{appKey}/events/search|

**[Path Variable]**

|Key|	Value|
|---|---|
|appKey|	[CONSOLE] 에서 발급받은 AppKey|

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
| idNo | String | X | Event를 발생시킨 회원 IdNo (uuid) |
| eventId | String | O | 조회할 Event의 ID |
| startDate | Date | O | 조회할 기간의 시작 날짜 |
| endDate | Date |O  | 조회활 기간의 끝나는 날짜 |
| page | Object | O | 조회 결과의 Page 조건 |
| page.sortBy | String | X | 조회 결과의 사이즈 정렬 조건 |
| page.limit | Integer | O | 조회 결과의 사이즈 조건 |
| page.page | Integer | O | 조회 결과의 Page중 조회 하고자 하는 Page 조건 |


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
                "userName": "홍길동",
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
                            "name": "임꺽정",
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
