# Session



## Create session

v1/github.auth/createSession

token - GitHub token&#x20;

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/github.auth/createSession",
  "sid": 1,
  "d": {
    "token": "XXX"
  }
}
```
{% endtab %}

{% tab title="Response error" %}
```json
{
  "sig": 2,
  "q": "v1/github.auth/createSession",
  "errorType": "401",
  "sid": 1,
  "d": {
    "errorCode": 6000,
    "errorMessage": "Authentication failed"
  }
}
```
{% endtab %}
{% endtabs %}
