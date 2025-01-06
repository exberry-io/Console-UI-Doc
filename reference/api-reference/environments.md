# Environments

## Find environment by name

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/environments/findEnvironmentByName",
  "sid": 1,
  "d": {
    "site": "uat-site",
    "environment": "uat-ops"
  }
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "q": "v1/environments/findEnvironmentByName",
  "sid": 1,
  "d": {
    "id": 3,
    "site": "uat-site",
    "environment": "uat-ops",
    "workspace": {
      "id": "d69e8fbe-12c7-48dc-b340-e7c8dc9cf3e6",
      "namespace": "shared",
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
          "id": 5,
          "name": "uat-ops",
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
          "id": 8,
          "name": "postgres-mp-service-shared",
          "type": "RDS",
          "ownershipType": "SHARED"
        },
        {
          "id": 21,
          "name": "postgres-project-service-shared",
          "type": "RDS",
          "ownershipType": "SHARED"
        }
      ],
      "services": [
        {
          "owner": "exberry-io",
          "repo": "mp-service",
          "configuration": {}
        },
        {
          "owner": "exberry-io",
          "repo": "project-service",
          "configuration": {}
        },
        {
          "owner": "exberry-io",
          "repo": "exchange-backoffice",
          "configuration": {
            "TOLERATION": "cloud",
            "DISCOVERY_AGENT_VERSION": "1.3.0"
          }
        }
      ],
      "configuration": {
        "TOLERATION": "cloud"
      },
      "lastModified": "2022-08-31T07:13:48.146"
    },
    "exchanges": [
      {
        "id": 200,
        "name": "exchange"
      },
      {
        "id": 202,
        "name": "toms"
      }
    ]
  }
}
```

## Add environment


{% endtab %}
{% endtabs %}

## ? Add environment



#### _Notes:_

* "_branch_" field is mandatory if "_deploymentType_": "**BRANCH**".
* "_branch_" field should not be included if "_deploymentType_" is "**PRERELEASE**" or "**RELEASE**".

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/environments/addEnvironment",
  "sid": 1,
  "d": {
    "site": "site",
    "environment": "environment",
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
```
// Some code
```
{% endtab %}
{% endtabs %}

## ? Update environment

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/environments/updateEnvironment",
  "sid": 1,
  "d": {
    "site": "site",
    "environment": "environment",
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
```
// Some code
```
{% endtab %}
{% endtabs %}
