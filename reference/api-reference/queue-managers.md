# Call Queue Managers


## Call Queue Manager By Id

{% swagger method="get" path="/queue-managers/{recordId}" baseUrl="https://api.voxo.co" summary="Retrieve queue manager by Id" %}
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
    "id": 5,
    "queueId": 298,
    "userId": 1362,
    "userEmail": "fred@gmail.com",
    "timezone": null,
    "userRole": 3,
    "receiveReports": 0
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/queue-managers/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}



## Call All Queue Managers

{% swagger method="get" path="/queue-managers?queueId={queueId}" baseUrl="https://api.voxo.co" summary="Retrieve queue managers for a specific queue Id. " %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="queueId" required="true" type="Integer" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
    {
        "id": 5,
        "queueId": 298,
        "userId": 1362,
        "userEmail": "fred@gmail.com",
        "timezone": null,
        "userRole": 3,
        "receiveReports": 0
    },
    {
        "id": 32,
        "queueId": 298,
        "userId": 1390,
        "userEmail": "cobra2335@yahoo.com",
        "timezone": "America/Chicago",
        "userRole": 7,
        "receiveReports": 0
    },
    {
        "id": 36,
        "queueId": 298,
        "userId": 797,
        "userEmail": "docharrod85@gmail.com",
        "timezone": "America/Chicago",
        "userRole": 3,
        "receiveReports": 1
    }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/queue-managers?queueId=298' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}

