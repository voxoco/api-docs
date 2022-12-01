# VOXO Meet

## Voxo Meet Credentials

{% swagger method="get" path="/voxo-meet-creds?ext={extNum}&tenantId={tenantId}" baseUrl="https://api.voxo.co" summary="Receive VOXO web and dial in meet credentials" %}
{% swagger-description %}

{% endswagger-description %}

{% swagger-parameter in="header" name="Authorization" required="true" type="String" %}
Bearer {accessToken}
{% endswagger-parameter %}

{% swagger-parameter in="header" name="Content-Type" required="true" type="String" %}
application/json
{% endswagger-parameter %}

{% swagger-parameter in="query" name="tenantId" required="true" %}
Integer
{% endswagger-parameter %}

{% swagger-parameter in="extNum" name="tenantId" required="true" %}
Integer
{% endswagger-parameter %}

{% swagger-response status="200: OK" description="" %}
```javascript
{
    "meetURL": "https://meet.voxo.co/shangadang",
    "dialIn": "1.601.602.5068 PIN: 3876287805#"
}
```
{% endswagger-response %}
{% endswagger %}


{% tabs %}
{% tab title="cURL" %}
```javascript
curl --location -g \
--request GET 'https://api.voxo.com/voxo-meet-creds?ext=1001&tenantId=37' \
--header 'Content-Type: application/json' \
--header 'Authorization: Bearer {accessToken}'
```
{% endtab %}
{% endtabs %}
