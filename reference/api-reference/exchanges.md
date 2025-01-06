# Exchanges

## Find Exchange by Name

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/environments/findExchangeByName",
  "sid": 1,
  "d": {
    "site": "uat-site",
    "environment": "uat-ops",
    "exchange": "exchange"
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "q": "v1/environments/findExchangeByName",
  "sid": 1,
  "d": {
    "id": 200,
    "site": "uat-site",
    "environment": "uat-ops",
    "exchange": "exchange",
    "workspace": {
      "id": "25782bd9-cc26-4c90-a58a-35d44d6aab2c",
      "namespace": "sandbox",
      "deploymentType": "RELEASE",
      "resources": [
        {
          "id": 2,
          "name": "vault",
          "type": "VAULT",
          "ownershipType": "SHARED"
        },
        {
          "id": 3,
          "name": "kafka-site",
          "type": "MSK",
          "ownershipType": "SHARED"
        },
        {
          "id": 6,
          "name": "uat-exchange",
          "type": "EKS",
          "ownershipType": "SHARED"
        },
        {
          "id": 7,
          "name": "postgres-history-service-shared",
          "type": "RDS",
          "ownershipType": "SHARED"
        },
        {
          "id": 13,
          "name": "algorand-shared",
          "type": "ALGORAND",
          "ownershipType": "SHARED"
        },
        {
          "id": 14,
          "name": "aws-shared",
          "type": "ACCOUNT",
          "ownershipType": "SHARED"
        },
        {
          "id": 20,
          "name": "postgres-oms-history-service-shared",
          "type": "RDS",
          "ownershipType": "SHARED"
        }
      ],
      "services": [
        {
          "owner": "exberry-io",
          "repo": "exchange-gateway",
          "configuration": {
            "TOLERATION": "gateways",
            "RESOURCES_REQUESTS_STORAGE": "20Gi",
            "RESOURCES_LIMITS_MEMORY": "2Gi",
            "RESOURCES_REQUESTS_MEMORY": "2Gi",
            "JAVA_OPTS": "-javaagent:/opt/exchange/lib/aeron-agent-1.35.1.jar -Daeron.event.log=admin -Daeron.event.archive.log=all",
            "SETTINGS": "io.exberry.exchange.gateway.createSessionTtl=60s"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "fix-gateway",
          "configuration": {
            "TOLERATION": "gateways"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-market-service",
          "configuration": {
            "TOLERATION": "market",
            "RESOURCES_REQUESTS_MEMORY": "2Gi",
            "RESOURCES_LIMITS_MEMORY": "2Gi",
            "JAVA_OPTS": "-XX:MaxRAMPercentage=50",
            "SETTINGS": "io.exberry.exchange.market.service.orderBookDepthWithPublicMarketParticipantId=false;io.exberry.exchange.market.service.recordingTermLength=65536"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-event-publisher",
          "configuration": {
            "TOLERATION": "publishers",
            "JAVA_OPTS": "-XX:MaxRAMPercentage=50",
            "SETTINGS": "io.exberry.exchange.event.publisher.baseDir=/opt/exchange;io.exberry.exchange.event.publisher.topics=order_events:10:2,market_events:1:2,indicative_price_events:1:2"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-operation-gateway",
          "configuration": {
            "TOLERATION": "gateways"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-history-service",
          "artifact": "history-service",
          "configuration": {
            "TOLERATION": "history",
            "SETTINGS": "io.exberry.exchange.history.service.reportsS3BucketName=exberry-reports-uat"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-history-service",
          "artifact": "history-service-persister",
          "configuration": {
            "TOLERATION": "history"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "oms-service",
          "configuration": {
            "TOLERATION": "market",
            "RESOURCES_REQUESTS_STORAGE": "200Gi",
            "RESOURCES_REQUESTS_MEMORY": "2Gi",
            "RESOURCES_LIMITS_MEMORY": "2Gi",
            "SETTINGS": "io.exberry.oms.service.mpId=2099106036;io.exberry.oms.service.recordingTermLength=65536"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "oms-history-service",
          "artifact": "oms-history-service",
          "configuration": {
            "TOLERATION": "history",
            "SETTINGS": "io.exberry.oms.history.service.reportsS3BucketName=nebula-reports-uat"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "oms-history-service",
          "artifact": "oms-history-service-persister",
          "configuration": {
            "TOLERATION": "history"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "oms-algorand-conductor",
          "configuration": {
            "TOLERATION": "publishers"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "oms-fix-gateway",
          "configuration": {
            "TOLERATION": "gateways"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "oms-trading-gateway",
          "artifact": "oms-trading-gateway",
          "configuration": {
            "TOLERATION": "gateways",
            "SETTINGS": "io.exberry.oms.trading.gateway.mpId=2099106036;io.exberry.oms.trading.gateway.tradingJwksUri=https://nebula-uat-exberry.eu.auth0.com/.well-known/jwks.json"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-market-data-service",
          "artifact": "market-data-service-external",
          "configuration": {
            "TOLERATION": "gateways",
            "RESOURCES_REQUESTS_MEMORY": "4Gi",
            "RESOURCES_LIMITS_MEMORY": "4Gi",
            "SETTINGS": "io.exberry.exchange.market.data.service.internalVisibility=false;io.exberry.exchange.market.data.service.maxTrades=500"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-market-data-service",
          "artifact": "market-data-service-internal",
          "configuration": {
            "TOLERATION": "gateways",
            "RESOURCES_REQUESTS_MEMORY": "4Gi",
            "RESOURCES_LIMITS_MEMORY": "4Gi",
            "SETTINGS": "io.exberry.exchange.market.data.service.internalVisibility=true;io.exberry.exchange.market.data.service.maxTrades=500"
          }
        }
      ],
      "configuration": {
        "JAVA_OPTS": "-XX:MaxRAMPercentage=80"
      },
      "lastModified": "2022-07-29T11:54:21.454"
    }
  }
}
```
{% endtab %}
{% endtabs %}

## Add Exchange



#### _Notes:_

* "_branch_" field is mandatory if "_deploymentType_": "**BRANCH**".
* "_branch_" field should not be included if "_deploymentType_" is "**PRERELEASE**" or "**RELEASE**".

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/environments/addExchange",
  "sid": 1,
  "d": {
    "site": "site",
    "environment": "environment",
    "exchange": "exchange",
    "namespace": "namespace",
    "deploymentType": "BRANCH|PRERELEASE|RELEASE",
    "branch": "knownbranch",
    "resources": [
      "abc"
    ],
    "services": [
      {
        "owner": "exberry-io",
        "repo": "abc-service",
        "configuration": {
          "io.acme.foo": "bar"
        }
      }
    ],
    "configuration": {
      "io.acme.bar": "baz"
    }
  }
}
```


{% endtab %}

{% tab title="Response" %}

{% endtab %}
{% endtabs %}

## ? Update Exchange

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/environments/updateExchange",
  "sid": 1,
  "d": {
    "site": "site",
    "environment": "environment",
    "exchange": "exchange",
    "resources": [
      "abc"
    ],
    "services": [
      {
        "owner": "exberry-io",
        "repo": "abc-service",
        "configuration": {
          "io.acme.foo": "bar"
        }
      }
    ],
    "configuration": {
      "io.acme.bar": "baz"
    }
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
// Some code
```
{% endtab %}
{% endtabs %}
