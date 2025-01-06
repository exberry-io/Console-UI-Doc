# Edit Service

On Edit service only "Artifact" field is allowed be changed from "Service details" container.

Service configurations can be edited as well, see [Edit configurations](edit-configurations.md).&#x20;

## API

Edit Service should use the "update" entity method from API (updateSite, updateEnvironment or updateExchange). The request payload should contain all existing resources (only names) and all existing services (without "version" attribute).&#x20;

