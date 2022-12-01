# Phone Numbers (DID)

## Get Phone Number By Id

{% swagger method="get" path="/dids/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve phone number (DID) by Id" %}
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
    "id": 6283,
    "tenantId": 432,
    "number": "6012028038",
    "namePrefix": "",
    "branchId": null,
    "diCommentName": "Grease Collector",
    "allowEmergency": "on",
    "branch": "",
    "tenantName": "The White House",
    "useStatus": "Available"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/dids/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## Get All Phone Numbers

{% swagger method="get" path="/dids?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve phone numbers (DIDs) for authorized accounts" %}
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
        "id": 6283,
        "tenantId": 432,
        "number": "6012028038",
        "namePrefix": "",
        "branchId": null,
        "diCommentName": "Grease Collector",
        "allowEmergency": "on",
        "branch": "",
        "tenantName": "The White House",
        "useStatus": "Available"
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/dids?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
