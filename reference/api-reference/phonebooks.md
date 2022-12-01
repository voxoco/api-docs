# Phonebooks



## Get Phonebook By Id

{% swagger method="get" path="/phonebooks/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve phone book by Id" %}
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
    "id": 2,
    "name": "OMNIA-1004",
    "includeExt": "no",
    "tenantId": 37
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/phonebooks/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}




## Get All Phonebooks

{% swagger method="get" path="/phonebooks?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve phone book list for authorized accounts" %}
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
        "id": 2,
        "name": "OMNIA-1004",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 95,
        "name": "OMNIA-1007",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 183,
        "name": "0004f2c6a3cb",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 781,
        "name": "0004f2cb02e5",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 939,
        "name": "Default",
        "includeExt": "yes",
        "tenantId": 37
    },
    {
        "id": 973,
        "name": "0004f28c07ea",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 991,
        "name": "test",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 1349,
        "name": "64167f0df998",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 1353,
        "name": "0004f27eb969",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 1579,
        "name": "OMNIA-1001",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 1587,
        "name": "billy",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 1588,
        "name": "fred",
        "includeExt": "no",
        "tenantId": 37
    },
    {
        "id": 1595,
        "name": "OMNIA-5193",
        "includeExt": "no",
        "tenantId": 37
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/phonebooks?tenantId=37' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
