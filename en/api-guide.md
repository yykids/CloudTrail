
## CloudTrail > API Guide

> By calling RESTful API to Cloud Trail, events can be queried by user-defined conditions. 

## URL & Appkey
AppKey is required to use RESTful API. 
Check your key information on top right of the [CONSOLE]. 
![[그림 1] AppKey & SecretKey 확인](http://static.toastoven.net/prod_cloudtrail/cloudtrail_20190924.png)

<center>[Figure 1] Check AppKeys </center>

## RESTful API Guide 

### Common Response Body

To all API requests, HTTP sends 200 for response code. 
Read the header at Response Body for more details of the response result.

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
|header|	Object| Response header |
|header.isSuccessful|	boolean| Successful or not |
|header.resultCode|	int| Response code: 0 for successful; error code returned if it fails |
|header.resultMessage|	String| Response message: "SUCCESS" if successful; or, error code returned if it fails. |

### 1. Query Events 
* Query events that occur. 
* Query events by user-defined search conditions.
* Request Body must include the search conditions. 

**[Method, URL]**

|Method|	URI|
|---|---|
|POST|	/cloud-trail/v1.0/appkeys/{appKey}/events/search|

**[Path Variable]**

|Key|	Value|
|---|---|
|appKey| Appkey issued on [CONSOLE] |

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
* member에 값을 지정하지 않으면 전체 이벤트 목록을 조회할 수 있습니다.
* TOAST memberType일 경우, emailAddress의 값은 필수이고, userCode의 값은 존재하지 않아야 합니다. 
* 반대로, IAM memberType일 경우, userCode의 값은 필수이고, emailAddress의 값은 존재하지 않아야 합니다.
* idNo 값이 있을 경우, memberType 과 userCode, emailAddress 값과 관계없이 우선적으로 적용됩니다.
* eventId에 대한 자세한 정보는 메뉴얼 참고 : [링크](http://beta-docs.toast.com/en/CloudTrail/en/event-list/)

| Key | Type | Required  | Description |
| --- | --- | --- | --- |
| idNo | String | X | ID of the member incurring an event (uuid) |
| eventId | String | O | ID of an event to query |
| startDate | Date | O | Start date of query period |
| endDate | Date |O  | End date of query period |
| page | Object | O | Page conditions of query result |
| page.sortBy | String | X | Size sorting conditions of query result |
| page.limit | Integer | O | Size conditions of query result |
| page.page | Integer | O | Page conditions to query among result pages |


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
                "userName": "Hong kildong",
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
                            "name": "Lim kkukjeong",
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