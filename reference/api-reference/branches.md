# Account Branches

## Get Account Branches by Id

{% swagger method="get" path="/branches/{branchId}" baseUrl="https://api.voxo.co" summary="Retrieve a single branch with specified account id" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="path" name="branchId" required="true" type="Integer" %}
1234
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "id": 758,
    "tenantId": 432,
    "name": "Executive"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
All branches for account id 432 are returned

```javascript
curl --location -g --request GET 'https://api.voxo.com/branches/123' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## Get All Account Branches

{% swagger method="get" path="/branches?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve all account branches for a specified account id" %}
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
        "id": 758,
        "tenantId": 432,
        "name": "Executive"
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
All branches for account id 432 are returned

```javascript
curl --location -g --request GET 'https://api.voxo.com/branches?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


