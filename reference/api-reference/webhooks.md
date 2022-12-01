# Webhooks

## Get Webhook By Id

{% swagger method="get" path="/webhooks/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve active webhooks by Id" %}
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
    "id": 23,
    "tenantId": 432,
    "type": "STARTCALL",
    "url": "https://voxo.co",
    "username": "fred",
    "password": "durst",
    "authtoken": "1234"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/webhooks/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}



## Get Webhooks

{% swagger method="get" path="/webhooks?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve active webhooks for authorized accounts." %}
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
        "id": 23,
        "tenantId": 432,
        "type": "STARTCALL",
        "url": "https://voxo.co",
        "username": "fred",
        "password": "durst",
        "authtoken": "1234"
    },
    {
        "id": 24,
        "tenantId": 432,
        "type": "ENDCALL",
        "url": "https://voxo.co",
        "username": "fred",
        "password": "durst",
        "authtoken": "1234"
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/webhooks?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}

