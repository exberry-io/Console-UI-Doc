# UI  

### Details
* Name - free text
* Cloud - radio buttons: `AWS` (default), `GCP` (disabled)
* Region - free text, autocomplete with values from config
* Account - free text
* Dry run - checkbox, default false, disabled (to be implemented in #214)


### Infra Info
* Owner - free text, default value `exberry-io`
* Repo - free text, default value `infrastructure`
* Version - free text, autocomplete, values from Github tags, sorted descending, default selected first item
* Module - free text, autocomplete, values are directories from Github source code of selected Version⚠ 
* Props - JSON editor, default value to be loaded from Github (`Repo` + `Module` + `Version`+ `template.json` file)


## Submit
* Build the JSON 
* Send to API `addInfrastructure`
* Show "in progress" status until the Success or Error is received
* Display in a multi-line read-only field the value from `data` (this is a string containing some log info), `status=RUNNING` for these messages
* On Success - display the "Success" message below "Logs" field
* On Error - display the "Error" message below "Logs" field
* User can close the page by clicking on "Close" button
