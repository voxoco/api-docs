# Number Porting Orders

## Get Port In Order By Id

{% swagger method="get" path="/port-in-orders/{orderId}" baseUrl="https://api.voxo.co" summary="Retrieve a single port order by id" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="path" name="orderId" required="true" type="Integer" %}

{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "orderId": 1349286,
  "customerOrderReference": "demo-687",
  "orderStatus": "Closed",
  "desiredDueDate": "2020-07-13T00:00:00.000+00:00",
  "tnGroups": [
    {
      "telephoneNumber": "6012491040",
      "tnStatus": "Complete",
      "streetNum": "900",
      "streetPreDir": "",
      "streetName": "Cherry Street",
      "streetType": "",
      "locationType": "",
      "locationNumber": "",
      "city": "Summit",
      "state": "MS",
      "postalCode": "39666",
      "tnGroup": "Group ID 323147 - AT&T Wireline (BellSouth)/1",
      "name": "TT",
      "trunkGroup": "RCFRILRC123_1045",
      "accountNum": "123456",
      "atn": "6012491040",
      "accountPin": "9999",
      "authName": "Freddie",
      "authDate": "2020-07-09T05:00:00.000+00:00"
    }
  ]
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/port-in-orders/1234' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## All Port In Orders

{% swagger method="get" path="/port-in-orders?orderRef={tenantId}" baseUrl="https://api.voxo.co" summary="Retrieve all port orders for a specific account" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="orderRef" required="true" type="Integer" %}
tenantId
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
    {
        "orderId": 1349294,
        "orderStatus": "Closed",
        "customerOrderReference": "demo-687",
        "desiredDueDate": "2020-07-13T00:00:00.000+00:00",
        "tnQuantity": 1,
        "createdDate": "2020-07-10T00:00:00.000+00:00",
        "createdUser": "api_user",
        "focTnQuantity": 0,
        "rejectedTnQuantity": 0,
        "activatedTnQuantity": 1,
        "focList": {
            "focItem": [
                {
                    "tnQuantity": 1,
                    "focTnQuantity": 0,
                    "rejectedTnQuantity": 0,
                    "activatedTnQuantity": 1
                }
            ]
        }
    },
    {
        "orderId": 1349286,
        "orderStatus": "Closed",
        "customerOrderReference": "demo-687",
        "desiredDueDate": "2020-07-13T00:00:00.000+00:00",
        "tnQuantity": 1,
        "createdDate": "2020-07-10T00:00:00.000+00:00",
        "createdUser": "api_user",
        "focTnQuantity": 0,
        "rejectedTnQuantity": 0,
        "activatedTnQuantity": 1,
        "focList": {
            "focItem": [
                {
                    "tnQuantity": 1,
                    "focTnQuantity": 0,
                    "rejectedTnQuantity": 0,
                    "activatedTnQuantity": 1
                }
            ]
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
--request GET 'https://api.voxo.com/port-in-orders?orderRef=demo' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
