# Sites

## Add site

v1/sites/addSite

#### _Notes:_

* "_branch_" field is mandatory if "_deploymentType_": "**BRANCH**".
* "_branch_" field should not be included if "_deploymentType_" is "**PRERELEASE**" or "**RELEASE**".

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/sites/addSite",
  "sid": 1,
  "d": {
    "name": "site",
    "namespace": "namespace",
    "deploymentType": "BRANCH|PRERELEASE|RELEASE",
    "branch": "knownbranch",
    "resources": [
      "eks"
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
{% endtabs %}

## Find site by ID

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "vs1/sites/findSiteById",
  "sid": 1,
  "d": 1
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "q": "v1/sites/findSiteById",
  "sid": 1,
  "d": {
    "id": 1,
    "name": "xyz-site",
    "workspace": {
      "id": "9b5b11c7-aaab-4422-880e-542dc60d1394",
      "namespace": "xyz",
      "deploymentType": "RELEASE",
      "resources": [
        {
          "id": 42,
          "name": "xyz-site",
          "type": "EKS",
          "ownershipType": "SHARED"
        },
        {
          "id": 43,
          "name": "vault-xyz",
          "type": "VAULT",
          "ownershipType": "SHARED"
        },
        {
          "id": 55,
          "name": "rdsxyz",
          "type": "RDS",
          "ownershipType": "SHARED"
        },
        {
          "id": 56,
          "name": "postgres-iam-service-xyz",
          "type": "RDS",
          "ownershipType": "SHARED"
        }
      ],
      "services": [
        {
          "owner": "exberry-io",
          "repo": "api-gateway",
          "configuration": {
            "SETTINGS": "io.exberry.exchange.api.gateway.createSessionTtl=60s;io.exberry.exchange.api.gateway.omsTraderAuth0Tenant=trading-release-exberry.eu.auth0.com;io.exberry.exchange.api.gateway.omsAdminAuth0Tenant=admin-release-exberry.eu.auth0.com"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "iam-service",
          "configuration": {}
        },
        {
          "owner": "exberry-io",
          "repo": "discovery",
          "configuration": {}
        }
      ],
      "configuration": {
        "TOLERATION": "cloud",
        "SITE_DNS": "xyz.exberry-dev.io",
        "SITE_ENTRYPOINT": "internal",
        "LOG4J_FORMAT_MSG_NO_LOOKUPS": "true",
        "SITE_NAME": "xyz-site"
      },
      "firstCreated": "2022-06-20T19:46:19.201",
      "lastModified": "2022-06-29T15:30:40.796"
    },
    "environments": [
      {
        "id": 1,
        "name": "xyz-ops"
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}

## Find site by name

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/sites/findSiteByName",
  "sid": 1,
  "d": "xyz-site"
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "q": "v1/sites/findSiteByName",
  "sid": 1,
  "d": {
    "id": 1,
    "name": "xyz-site",
    "workspace": {
      "id": "9b5b11c7-aaab-4422-880e-542dc60d1394",
      "namespace": "xyz",
      "deploymentType": "RELEASE",
      "resources": [
        {
          "id": 42,
          "name": "xyz-site",
          "type": "EKS",
          "ownershipType": "SHARED"
        },
        {
          "id": 43,
          "name": "vault-xyz",
          "type": "VAULT",
          "ownershipType": "SHARED"
        },
        {
          "id": 55,
          "name": "rdsxyz",
          "type": "RDS",
          "ownershipType": "SHARED"
        },
        {
          "id": 56,
          "name": "postgres-iam-service-xyz",
          "type": "RDS",
          "ownershipType": "SHARED"
        }
      ],
      "services": [
        {
          "owner": "exberry-io",
          "repo": "api-gateway",
          "configuration": {
            "SETTINGS": "io.exberry.exchange.api.gateway.createSessionTtl=60s;io.exberry.exchange.api.gateway.omsTraderAuth0Tenant=trading-release-exberry.eu.auth0.com;io.exberry.exchange.api.gateway.omsAdminAuth0Tenant=admin-release-exberry.eu.auth0.com"
          }
        },
        {
          "owner": "exberry-io",
          "repo": "iam-service",
          "configuration": {}
        },
        {
          "owner": "exberry-io",
          "repo": "discovery",
          "configuration": {}
        }
      ],
      "configuration": {
        "TOLERATION": "cloud",
        "SITE_DNS": "xyz.exberry-dev.io",
        "SITE_ENTRYPOINT": "internal",
        "LOG4J_FORMAT_MSG_NO_LOOKUPS": "true",
        "SITE_NAME": "xyz-site"
      },
      "firstCreated": "2022-06-20T19:46:19.201",
      "lastModified": "2022-06-29T15:30:40.796"
    },
    "environments": [
      {
        "id": 1,
        "name": "xyz-ops"
      }
    ]
  }
}
```
{% endtab %}
{% endtabs %}

## Find all sites

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/sites/findAllSites",
  "sid": 1
}
```
{% endtab %}

{% tab title="Response" %}
```json
{
  "q": "v1/sites/findAllSites",
  "sid": 1,
  "d": [
    {
      "id": 1,
      "name": "xyz-site",
      "workspace": {
        "id": "9b5b11c7-aaab-4422-880e-542dc60d1394",
        "cluster": "xyz-site",
        "namespace": "xyz",
        "deploymentType": "RELEASE"
      }
    }
  ]
}
```
{% endtab %}
{% endtabs %}

## Update site

The request should include all resources which should remain after update.&#x20;

* to add a new resource - include all existing resources + the new one
* to remove the resource - include all existing resources, excluding the desired one



{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/sites/updateSite",
  "sid": 1,
  "d": {
    "name": "site",
    "resources": [
      "eks"
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
{% endtabs %}
