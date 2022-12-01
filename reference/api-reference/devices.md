# Devices

## Get Device By Id

{% swagger method="get" path="/devices/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve single device by Id" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="path" name="recordId" required="true" type="Integer" %}
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "id": 34,
    "tenantId": 432,
    "name": "2043",
    "mac": "00:00:00:00:00:00",
    "phLine1ExId": 160,
    "phPmId": 22,
    "deviceModel": "Polycom",
    "phonebookIds": [
        2,
        253,
        905
    ],
    "tenantName": "The White House",
    "tenantCode": "the"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/devices/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## Get All Devices

{% swagger method="get" path="/devices/?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve devices registered to an authorized tenant account" %}
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
        "id": 34,
        "tenantId": 432,
        "name": "2043",
        "mac": "00:00:00:00:00:00",
        "phLine1ExId": 160,
        "phPmId": 22,
        "deviceModel": "Polycom",
        "phonebookIds": [
            2,
            253,
            905
        ],
        "tenantName": "The White House",
        "tenantCode": "the"
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/devices/?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
