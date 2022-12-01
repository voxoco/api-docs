# Call Reports (CDR)

## Get Call Reports

{% swagger method="get" path="/call-reports" baseUrl="https://api.voxo.co" summary="" %}
{% swagger-description %}
Return the call detail records for an account for a specified date range. The max range allowed between start and end is 31 days.

This endpoint is valid for account admin, reports admin, and partner admin roles user and requires an access token. See [Authentication](authentication.md) for details on obtaining an access token.

**Partner admin accounts are not required to pass a billingCode or tenantId param. Data for this request will be limited to a 24 hour period.**


{% endswagger-description %}

{% swagger-parameter in="query" name="tenantId" required="true" type="Integer" %}
Id of the account for which to query records. Not required for partner admin users if billingCode is provided. See notes!
{% endswagger-parameter %}

{% swagger-parameter in="query" name="billingCode" %}
Required if tenantId not provided. Partner admin users only. See notes!
{% endswagger-parameter %}

{% swagger-parameter in="query" name="start" required="true" %}
start date - YYYY-MM-DD HH:MM:SS
{% endswagger-parameter %}

{% swagger-parameter in="query" name="end" required="true" type="" %}
end date - YYYY-MM-DD HH:MM:SS
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="query" name="timezone" %}
Timezone of the requested start and end dates. Defaults to America/Chicago if not included.
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="false" %}
application/json
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
    {
        "id": "2d275d62-706c-42d2-a4d4-e4ef53d83974",
        "time": "10/10/22 23:07:20",
        "callerIdNumber": "5555555555",
        "callerIdName": "BILL CLINTON",
        "dialedNum": "5555555555",
        "direction": "IN",
        "disposition": "ANSWERED",
        "duration": 4,
        "percentJitter": 0,
        "packetLoss": 0,
        "qos": 0,
        "uniqueId": "atl-ast2-1665457640.1430167",
        "prevUniqueId": "",
        "whoAnswered": "",
        "recorded": 0,
        "queueCall": 0,
        "ocn": "8911",
        "ani": "5555555555",
        "lata": "826",
        "city": "KINGSTON",
        "rateCenter": "KINGSTON",
        "state": "JM",
        "jurisdiction": "INTERSTATE",
        "local": 0,
        "lec": "JAMAICA TELEPHONE CO.",
        "lecType": "CLEC",
        "spid": null,
        "isTollFree": null,
        "nextUniqueId": "",
        "isInternational": null,
        "presented": 1,
        "mos": 0,
        "callOutcome": "",
        "afterAnswerDuration": 4,
        "outgoingCidNum": null,
        "billingId": null,
        "partnerId": null,
        "geolocation": null
    },
    {
        "id": "ae8a5f62-7bd3-46a0-84d6-a3d46b35c886",
        "time": "10/10/22 19:49:16",
        "callerIdNumber": "5555555555",
        "callerIdName": "FRED DURST",
        "dialedNum": "5555555555",
        "direction": "IN",
        "disposition": "NO ANSWER",
        "duration": 3,
        "percentJitter": 0,
        "packetLoss": 0,
        "qos": 1,
        "uniqueId": "atl-ast2-1665445756.1422469",
        "prevUniqueId": "",
        "whoAnswered": "",
        "recorded": 0,
        "queueCall": 0,
        "ocn": null,
        "ani": null,
        "lata": null,
        "city": null,
        "rateCenter": null,
        "state": null,
        "jurisdiction": null,
        "local": null,
        "lec": null,
        "lecType": null,
        "spid": null,
        "isTollFree": null,
        "nextUniqueId": "",
        "isInternational": null,
        "presented": 0,
        "mos": 4.4,
        "callOutcome": "",
        "afterAnswerDuration": 0,
        "outgoingCidNum": null,
        "billingId": null,
        "partnerId": null,
        "geolocation": null
    },
]
```
{% endswagger-response %}
{% endswagger %}

Bearer

application/json

{% tabs %}
{% tab title="cURL" %}
```javascript
// Providing a Account Id (tenantId)
curl --location -g \
--request GET 'api.voxo.co/call-reports?tenantId=37&start=2022-10-10 00:00:00&end=2022-12-11 00:00:00&timezone=America/New_York' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer accessToken'

// Providing A Billing Code
curl --location -g \
--request GET 'api.voxo.co/call-reports?billingCode=XXXX&start=2022-10-10 00:00:00&end=2022-12-11 00:00:00&timezone=Europe/Dublin' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer accessToken'


// 24 Hour Range Request (All Partner CDR)
curl --location -g \
--request GET 'api.voxo.co/call-reports?start=2022-10-10 00:00:00&end=2022-12-11 00:00:00&timezone=Europe/Dublin' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer accessToken'
```
{% endtab %}
{% endtabs %}
