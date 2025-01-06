---
description: Wizard of 5 steps, all fields are mandatory by default
---

# Add Site/Environment/Exchange

## Step 1 - Type

**Type** - Single select:&#x20;

* Site
* Environment
* Exchange

**Destination**

* Site - dropdown with list of existing Sites, enabled when type is Environment or Exchange
* Environment -  dropdown with list of existing Environments of selected Site, enabled when type is Exchange

**Copy options**

Copy configurations from another item - checkbox, when it's selected then "source" should be selected.

When copy options is selected, and user navigates to the second step, all the details from the source item are copied to the current item, except Name and Namespace fields (see step 2).

After user navigates from Step 1 to Step 2, the Step 1 becomes read-only so no data can be changed there.&#x20;

## Step 2 - General details

**Details**

* Name
* Namespace
* Deployment type - dropdown, values are loaded from Config
* Branch - mandatory when Deployment type is "Branch", disabled when Deployment type is not "Branch"

**Link resources**&#x20;

A list of existing resources, with multiple select.

## Step 3 - Add services

**Services**

List of added services with single-select.

When the item is selected, then Service Details and Service Configurations sections below are populated with data of selected item.

**Service details**

* Owner
* Repository - auto-suggest with services from Config
* Artifact - auto-suggest with artifacts from Config

If there are any data on this section (for new or edit) and user is trying to navigate to another step, the system notifies about unsaved changes and blocks the navigation.

**Service Configuration**&#x20;

List of suggested keys are loaded from Config of the selected Service.



## Step 4 - Configurations

**Configurations**&#x20;

List of suggested keys are loaded from Config according to the selected entity type.



## Step 5 - Review and create

Information from all  steps are displayed in read-only mode for review.

For Step 1 shows the "info" section:

> **Create ENTITY\_TYPE**
>
> After submitting the current form, the ENTITY\_NAME ENTITY\_TYPE will be created.

When "Copy option" was used on step 1, then show the "info" section:

> **Source configurations**
>
> SITE\_NAME > ENV\_NAME > EXCH\_NAME

