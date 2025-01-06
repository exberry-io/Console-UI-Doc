# Add/Deploy Resource

Resources can be added in two ways:

* Deploy - which runs a deployment process and creates a record on MongoDB
* Add - which creates a record on MongoDB only

## Resource type configuration

{% code title="Configuration example" %}
```json
"RDS": {
	"label": "RDS",
	"actions": [
		"deploy",
		"add"
	],
	"requestMethod": "deployRds",
	"repos": [
		"terraform-rds-postgres"
	],
	"attributesTemplate": {
		"vault": "vault-xyz"
	},
	"deployPropsTemplate": {
		"vpc_name": "vpc123"
	}
},
```
{% endcode %}

{% code title="API request" %}
```json
{
  "q": "v1/resources/deployRds",
  "sid": 1,
  "d": {
    "name": "slava-rds-1",
    "ownershipType": "SHARED",
    "account": "develop",
    "region": "ap-southeast-1",
    "vault": "vault-xyz",
    "infraInfo": {
      "owner": "exberry-io",
      "repo": "terraform-rds-postgres",
      "version": "0.1.1"
    },
    "props": {
      "vpc_name": "xyz-site"
    }
  }
}
```
{% endcode %}

Label - the displayed value on UI

Actions - allowed action types

Request method - the action name for API when Deploy action is selected

Repos - the value for Repository field of Infrastructure info container

Attributes template - list of attributes which should be provided as part of "data" object in the request

Deploy Props template - list of attributes which should be provided as part of "props" object in the request



## Step 1 - Type

* Action - select the action:
  * Add & Deploy
  * Add
* Resource type - display the list resource types which has "Actions=deploy" in the config.

Once user navigates to the second step, the fields on step 1 are read-only.

## Step 2 - Details

### Basic details container

* Name - free text
* Ownership type - dropdown with values from Config
* Region - dropdown with list of AWS regions which are enabled for the account. For now it's free text since the Env Service API doesn't provide this info. Enabled only for Deploy action.
* Account - free text. Enabled only for Deploy action.

### Infrastructure info container

All fields of this container are enabled only for Deploy action.

* Owner - free text with default value "exberry-io"
* Repository - auto-suggest input with values from Config ("repo" attribute)
* Module - optional free text, the scope of this field is unknown.
* Version - the list of GitHub tags for the selected repository&#x20;

### Attributes

Code editor with content of "attributesTemplate" from config. Enabled and with values only for Deploy action. For Add action it's empty.

### Deploy properties

Code editor with content of "deployPropsTemplate" from config. Enabled and with values only for Deploy action. For Add action it's empty.



## Step 3 - Review

Information from all  steps are displayed in read-only mode for review.

For Step 1 shows the "info" section:

When Add type is selected:

> **Create RESOURCE\_TYPE**
>
> After submitting the current form, the RESOURCE\_NAME resource, of type RESOURCE\_TYPE will be created (Mongo record).

When Deploy type is selected:

> **Deploy RESOURCE\_TYPE**
>
> After submitting the current form, the RESOURCE\_NAME resource, of type RESOURCE\_TYPE will be deployed.

