# Paging Groups

## Get Paging Group By Id

{% swagger method="get" path="/paging-groups/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve paging group by Id" %}
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
    "id": 37,
    "tenantId": 432,
    "number": "3424",
    "name": "test",
    "twoWayAudio": "yes",
    "meId": 0,
    "checkInUse": "on",
    "pin": 0,
    "manualHeader": ""
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/paging-groups/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}



## Get All Paging Groups

{% swagger method="get" path="/paging-groups?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve the paging groups for authorized accounts" %}
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
        "id": 37,
        "tenantId": 432,
        "number": "3424",
        "name": "test",
        "twoWayAudio": "yes",
        "meId": 0,
        "checkInUse": "on",
        "pin": 0,
        "manualHeader": ""
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/paging-groups?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
