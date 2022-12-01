# Accounts

## Get Account By Id

{% swagger method="get" path="/tenants/{tenantid}" baseUrl="https://api.voxo.co" summary="Retrieve tenant account by id" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="path" name="tenantId" type="Integer" required="true" %}
1234
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "id": 432,
    "name": "The White House",
    "timeZone": "America/Chicago",
    "tenantCode": "the",
    "alertEmail": "NULL",
    "paymentType": "Post Paid",
    "disabled": "0",
    "maxChannels": -1,
    "allowAnyCallerIdForEmerg": "on",
    "te_cl_id": 0,
    "rpId": null,
    "te_billingcode": "NULL",
    "recordingStorage": "",
    "recordingHost": "",
    "recordingUser": "",
    "recordingPassword": "",
    "recordingDir": "",
    "te_defaultrrid": -1,
    "provisioningDir": "",
    "billDate": "2021-07-10",
    "parkingLot": {
        "id": 0,
        "name": "the",
        "start": 71,
        "end": 74,
        "hosted": "",
        "tenantId": 432
    },
    "settings": {
        "ADDITIONALDESTINATIONPEER": "caller",
        "CALLWAITING": "yes",
        "DEFAULTCALLERIDCF": "ORIGINAL",
        "DEFAULTTIMEOUTCF": "30",
        "DIALBYNAMEALWAYSPLAY": "no",
        "DIALBYNAMEUSENAMES": "all",
        "DIALBYNAMEUSEVMGREETING": "yes",
        "DIALTIMEOUT": "180",
        "EXTDIALTIMEOUT": "15",
        "FAKERINGING": "on",
        "FAXOUTPREFIX": "2329",
        "INTERNALRING": "Bellcore-dr2",
        "MAXCALLDURATION": "28800",
        "ONINTERNALCALLBUSY": "askforreservation",
        "PAGEINUSE": "CHECK",
        "PARKTIMEOUT": "120",
        "QUEUERING": "Bellcore-dr4",
        "RECORDINGBEEP": "on",
        "SMSSTORE": "yes",
        "TRANSFERRING": "Bellcore-dr1",
        "VMAUTORECOVER": "no",
        "VMSAMEPASSWORD": "no",
        "WEBCALLS": "no",
        "WORKINGHOURS": "0"
    },
    "integrations": [],
    "extensionsCount": 0,
    "didsCount": 0,
    "usersCount": 0,
    "callWaiting": "yes",
    "incomingRingsCount": "15",
    "parkinglotTimeout": "120",
    "enablePassword": "no",
    "parkinglot": 4,
    "webhooks": []
}
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}
Tenant account with id 432 is returned

```javascript
curl --location -g --request GET 'https://api.voxo.com/tenants/432' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}


## Get All Accounts

{% swagger method="get" path="/tenants" baseUrl="https://api.voxo.co" summary="Retrieve all tenant accounts" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
[
  {
    "id": 409,
    "name": "amon amarth",
    "timeZone": "America/Los_Angeles",
    "tenantCode": "amo"
  },
  {
    "id": 379,
    "name": "Box-Jenkins",
    "timeZone": "America/Chicago",
    "tenantCode": "box"
  },
  {
    "id": 432,
    "name": "The White House",
    "timeZone": "America/Chicago",
    "tenantCode": "the"
  }
]
```
{% endswagger-response %}
{% endswagger %}

{% tabs %}
{% tab title="cURL" %}

```javascript
curl --location -g --request GET 'https://api.voxo.com/tenants' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
