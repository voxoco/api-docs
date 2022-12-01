# Call Recordings

## Get Call Recordings Records

{% swagger method="get" path="/call-reports" baseUrl="https://api.voxo.co" summary="" %}
{% swagger-description %}
* Allows retrieving up to 2 days worth of call recording records
* Start and end timestamps are required along with the account id
* Returned timestamps are Central Time (CST)
{% endswagger-description %}

{% swagger-parameter in="query" name="recordType" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="recordings" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="start" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="end" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="query" name="tenantId" required="true" type="Integer" %}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="false" %}
application/json
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
    {
        "id": "f36bd91a-cd09-4770-b974-a92f6023164f",
        "start": "2021-08-13 19:36:59",
        "callerIdNumber": "1008",
        "callerIdName": "MRJINGLES",
        "dialedNum": "6016021302",
        "direction": "OUT",
        "disposition": "ANSWERED",
        "duration": 18,
        "percentJitter": 0,
        "packetLoss": 0,
        "qos": 1,
        "uniqueId": "atl-ast2-XXXX.XXX",
        "prevUniqueId": "",
        "whoAnswered": "6016021302",
        "recorded": 1
    },
    {
        "id": "10d891fd-00e6-47ba-a3e7-1c17a984ac7d",
        "start": "2021-08-13 19:35:41",
        "callerIdNumber": "1008",
        "callerIdName": "MRJINGLES",
        "dialedNum": "6016021302",
        "direction": "OUT",
        "disposition": "ANSWERED",
        "duration": 26,
        "percentJitter": 0,
        "packetLoss": 0,
        "qos": 1,
        "uniqueId": "atl-ast2-XXXX.XXX",
        "prevUniqueId": "",
        "whoAnswered": "6016021302",
        "recorded": 1
    },
    {
        "id": "7b7bf966-7f84-4a8b-af03-2928dce2cc0a",
        "start": "2021-08-13 19:33:05",
        "callerIdNumber": "1008",
        "callerIdName": "MRJINGLES",
        "dialedNum": "2192476000",
        "direction": "OUT",
        "disposition": "ANSWERED",
        "duration": 22,
        "percentJitter": 0.06,
        "packetLoss": 0,
        "qos": 1,
        "uniqueId": "atl-ast2-XXXX.XXX",
        "prevUniqueId": "",
        "whoAnswered": "2192476000",
        "recorded": 1
    }
]
```
{% endswagger-response %}
{% endswagger %}

Bearer

application/json

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/call-reports?recordType=recordings&start=2021-08-13 00:00:00&end=2021-08-14 00:00:00&tenantId=37' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}

## Get Call Recording Audio

{% swagger method="get" path="/call-recordings/{recording_unique_id}" baseUrl="https://api.voxo.co" summary="Returns URL to Call Recording" %}
{% swagger-description %}
Allow fetching of temporary URL to call recording

* URL expires after 60 seconds
* **Start timestamp must be provided as returned in the original call recording record**
* Returned timestamps are Central Time (CST)

{% endswagger-description %}

{% swagger-parameter in="path" name="uniqueId" required="true" %}
atl-ast2-XXXX.XXX
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tenantId" required="true" type="Integer" %}
1234
{% endswagger-parameter %}

{% swagger-parameter in="query" name="start" required="true" %}

{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="false" %}
application/json
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
  "uri": "https://global-recordings.s3.amazonaws.com/demo/2021/08/13/19/atl-ast2-XXXXXX.mp3?AWSAccessKeyId=AKIAJ6AZSMGK4FVBK4BQ&Expires=1629121111&Signature=9o2P1B0rm%2BqmRRTqJXEuAv6%2BUt0%3D"
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.co/call-recordings/atl-ast2-1628901419.8373?tenantId=14234545341&start=2021-08-13%2019:36:59' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}

