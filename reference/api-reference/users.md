# Users

## Get User By Id

{% swagger method="get" path="/users/{recordId}" baseUrl="https://api.voxo.co" summary="Fetch user by Id" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="path" name="recordId" required="true" type="Integer" %}
1234
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "id": 1392,
    "tenantId": 37,
    "receiveQueueReports": 0,
    "email": "jh@hu.com",
    "emailField": null,
    "avatarPath": null,
    "avatarFileName": null,
    "userRole": 5,
    "us_useldap": "",
    "resetToken": null,
    "online": 0,
    "lastOnline": null,
    "enableCallNotifications": 1,
    "enableChatNotifications": 0,
    "integrationId": null,
    "timezone": null,
    "adminQueues": [],
    "tenantIds": [],
    "name": "flka",
    "extNum": "90809"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/users/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## Get All Users

{% swagger method="get" path="/users/?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Fetch all users your user has access" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tenantId" required="true" type="Integer" %}
1234
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
    {
        "id": 1392,
        "tenantId": 37,
        "receiveQueueReports": 0,
        "email": "jh@hu.com",
        "emailField": null,
        "avatarPath": null,
        "avatarFileName": null,
        "userRole": 5,
        "us_useldap": "",
        "resetToken": null,
        "online": 0,
        "lastOnline": null,
        "enableCallNotifications": 1,
        "enableChatNotifications": 0,
        "integrationId": null,
        "timezone": null,
        "adminQueues": [],
        "tenantIds": [],
        "name": "flka",
        "extNum": "90809"
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/users/?tenantId=37' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
