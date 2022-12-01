# Custom Destinations

## Get Custom Destination By Id

{% swagger method="get" path="/customs/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve Custom Destination record by Id" %}
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
    "id": 47,
    "ctId": 1,
    "name": "Slingaling",
    "param1": "8552934892",
    "param2": "ORIGINAL",
    "param3": "",
    "param4": "",
    "param5": "",
    "param6": "",
    "param7": "",
    "param8": "",
    "param9": "",
    "param10": "",
    "tenantId": 432,
    "cu_ct_id": 1,
    "customType": {
        "id": 1,
        "name": "FORWARD"
    }
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/customs/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## Get All Custom Destinations

{% swagger method="get" path="/customs?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve Customs for authorized tenant accounts" %}
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
        "id": 47,
        "ctId": 1,
        "name": "Slingaling",
        "param1": "8552934892",
        "param2": "ORIGINAL",
        "param3": "",
        "param4": "",
        "param5": "",
        "param6": "",
        "param7": "",
        "param8": "",
        "param9": "",
        "param10": "",
        "tenantId": 432,
        "cu_ct_id": 1,
        "customType": {
            "id": 1,
            "name": "FORWARD"
        }
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/customs?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
