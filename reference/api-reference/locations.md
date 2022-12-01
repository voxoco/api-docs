# E911 Locations

## Get E911 Location By Id

{% swagger method="get" path="/locations/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve single E911 Location by Id" %}
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
    "diCommentName": "Grease Collector",
    "emergencyNotes": "{\"streetNum\":\"23\",\"streetInfo\":\"Cutlass Pt\",\"location\":\"\",\"city\":\"Hattiesburg\",\"state\":\"MS\",\"postalCode\":\"39402\"}",
    "namePrefix": "",
    "recording": "no",
    "fax": "no",
    "allowEmergency": "on",
    "tenantId": 432,
    "branch": "",
    "department": "",
    "number": "6012028038"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/locations/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}



## Get All E911 Locations

{% swagger method="get" path="/locations?tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve 911 Locations for a specific account" %}
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
        "diCommentName": "Grease Collector",
        "emergencyNotes": "{\"streetNum\":\"23\",\"streetInfo\":\"Cutlass Pt\",\"location\":\"\",\"city\":\"Hattiesburg\",\"state\":\"MS\",\"postalCode\":\"39402\"}",
        "namePrefix": "",
        "recording": "no",
        "fax": "no",
        "allowEmergency": "on",
        "tenantId": 432,
        "branch": "",
        "department": "",
        "number": "6012028038"
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/locations?tenantId=432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
