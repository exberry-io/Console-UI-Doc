# Resources

## ? Find All Resources

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/resources/findAllResources",
  "sid": 1
}
```
{% endtab %}

{% tab title="Response" %}

{% endtab %}
{% endtabs %}

## ? Find Resource by Name

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/resources/findResourceByName",
  "sid": 1,
  "d": "abc"
}
```
{% endtab %}

{% tab title="Response" %}

{% endtab %}
{% endtabs %}

## ? Add Resource

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/resources/addResource",
  "sid": 1,
  "d": {
    "name": "resource",
    "type": "EKS|VAULT|MSK|RDS|AUTH0|MONGO",
    "ownershipType": "DEDICATED|SHARED"
  }
}
```
{% endtab %}

{% tab title="Response" %}

{% endtab %}
{% endtabs %}

## ? Deploy EKS

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/resources/deployEks",
  "sid": 1,
  "d": {
    "cluster": "abc123",
    "clusterType": "NEBULA|SITE|ENVIRONMENT|EXCHANGE",
    "dnsSuffix": "abc.exberry.io",
    "defaultToleration": "qwerty",
    "ownershipType": "DEDICATED|SHARED",
    "account": "foobar",
    "region": "eu-west-2",
    "infraInfo": {
      "owner": "exberry-io",
      "repo": "terraform-eks-exberry-tenant",
      "module": null,
      "version": "ver1234"
    },
    "props": {
      "network_id": 256,
      "head_vpc_id": "headvpc123",
      "transit_gw_id": "tgw123",
      "dns_lb": "qwerty.exberry.io",
      "certificate_arn_ext": "arn:abc12345",
      "nodePools": {
        "kubsystem": {
          "taint": "qwerty",
          "count": 1,
          "minCount": 1,
          "maxCount": 8,
          "autoscaling": true,
          "instanceType": "t3a.small"
        }
      }
    }
  }
}
```
{% endtab %}

{% tab title="Second Tab" %}

{% endtab %}
{% endtabs %}

## ? Deploy Vault

{% tabs %}
{% tab title="Request" %}
```json
{
  "q": "v1/resources/deployVault",
  "sid": 1,
  "d": {
    "vault": "vault123",
    "cluster": "abc123",
    "namespace": "vault",
    "secretsBasePath": "secretv2",
    "serviceAccountTtl": "1h",
    "vaultVersion": "1.6.1",
    "vaultSize": "3",
    "vaultDbInstanceType": "db.t3.small",
    "quotaInfo": {
      "limitsCpu": "2",
      "limitsMemory": "2Gi",
      "requestsCpu": "2",
      "requestsMemory": "2Gi"
    },
    "ownershipType": "DEDICATED|SHARED",
    "infraInfo": {
      "owner": "exberry-io",
      "repo": "terraform-vault",
      "module": null,
      "version": "ver1234"
    },
    "props": {
      "vpc_name": "vpc123"
    }
  }
}
```
{% endtab %}

{% tab title="Response" %}

{% endtab %}
{% endtabs %}
