---
description: In order to make API requests, you will first need to request a token
---

# 🔑 Authentication

{% swagger method="post" path="/authentication" baseUrl="https://api.voxo.co" summary="This request returns an access token along with the authenticated user" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Accept" type="String" required="false" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="body" name="strategy" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="email" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-parameter in="body" name="password" required="true" type="String" %}

{% endswagger-parameter %}

{% swagger-response status="201: Created" description="" %}
```javascript
{
  "accessToken": "XXXXXXXXXXXXX",
  "authentication": {
    "strategy": "local"
  },
  "user": {
    "id": 0,
    "tenantId": 0,
    "receiveQueueReports": 0,
    "email": "test@test.com",
    "emailField": null,
    "avatarPath": null,
    "avatarFileName": null,
    "userRole": 1,
    "us_useldap": "",
    "resetToken": null,
    "online": 0,
    "lastOnline": "2020-09-28 15:46:02",
    "enableCallNotifications": 1,
    "enableChatNotifications": 0,
    "integrationId": null,
    "timezone": null,
    "conversations": [
      0
    ],
    "faxEnabled": false,
    "faxNumber": null,
    "myExtension": {
      "id": 0,
      "name": "Tony Fax",
      "tenantId": 0,
      "tenantCode": "demo",
      "number": "XXX",
      "sipFriendId": 0,
      "status": "NOT_INUSE",
      "hostServer": "",
      "peerName": "XXX",
      "peerSecret": "XXXX",
      "dnd": "",
      "callerId": "XXX",
      "voicemailId": 0,
      "omniaPhonebookId": null,
      "devices": [
        null
      ],
      "branch": "Hattiesburg",
      "branchId": 0,
      "queueIds": [
        0,
        0
      ]
    },
    "adminQueues": [],
    "tenantIds": [],
    "name": "Tony Fax",
    "extNum": "XXXX"
  }
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location --request POST 'https://api.voxo.co/authentication' \
--header 'Accept: application/json' \
--header 'Content-Type: application/json' \
--data-raw '{
	"strategy": "local",
	"email": "test@test.com",
	"password": "XXXX"
}'
```
{% endtab %}
{% endtabs %}

The response from this API will contain a field called `accessToken`

![](<../../.gitbook/assets/Screen Shot 2022-03-01 at 5.17.02 PM.png>)

All subsequent API calls should the following header

```
Authorization: Bearer {accessToken}
```

Replace `{accessToken}` with value from the response
