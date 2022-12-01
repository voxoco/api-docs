# Call Queues

## Call Queues

{% swagger method="get" path="/queues/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve call queue by Id" %}
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
    "id": 298,
    "tenantId": 37,
    "name": "Test Queue",
    "number": "",
    "hostServer": "atl-ast2",
    "recording": "no",
    "ringStrategy": "RINGALL"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/queues/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## Get All Call Queues

{% swagger method="get" path="/queues?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve queues for a specific account." %}
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
        "id": 298,
        "tenantId": 37,
        "name": "Test Queue",
        "number": "",
        "hostServer": "atl-ast2",
        "recording": "no",
        "ringStrategy": "RINGALL"
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/queues/?tenantId=37' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
