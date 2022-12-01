# Extensions

## Get Extension By Id

{% swagger method="get" path="/extensions/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve Extension by Id" %}
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
    "id": 5903,
    "name": "Grablic",
    "number": "1234",
    "cidNum": "6015515455",
    "branch": "",
    "branchId": null,
    "department": "",
    "emergencyCidNum": "",
    "unconditionalStatus": "",
    "email": "jut@tut.com",
    "tenantId": 432,
    "techId": 11208,
    "avatarPath": null,
    "userId": null,
    "userOnline": null,
    "peerName": "1234-the",
    "peerSecret": "XXXXXXX",
    "extStatus": "UNAVAILABLE",
    "hostServer": ""
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/extensions/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}

## Get All Extensions

{% swagger method="get" path="/extensions?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve extensions for account tenants you have access to" %}
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
        "id": 5903,
        "name": "Grablic",
        "number": "1234",
        "cidNum": "6015515455",
        "branch": "",
        "branchId": null,
        "department": "",
        "emergencyCidNum": "",
        "unconditionalStatus": "",
        "email": "jut@tut.com",
        "tenantId": 432,
        "techId": 11208,
        "avatarPath": null,
        "userId": null,
        "userOnline": null,
        "peerName": "1234-the",
        "peerSecret": "XXXXXXX",
        "extStatus": "UNAVAILABLE",
        "hostServer": ""
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/extensions?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
