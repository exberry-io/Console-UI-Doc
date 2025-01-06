# Applicatins

**Breadcrumb**: Applications

**Page title**: Applications (count)

**Action buttons**

* Add

**Display list with columns**:
* Name - d.name
* Resource Name - d.attributes.resourceName
* Module - d.attributes.infraInfo.module
* Version - d.attributes.infraInfo.version
* Last Modified - d.lastModified
* View - link which displays in a popup the entire info from d in JSON format (read-only)

**Split panel**

Column 1:
* First created - d.firstCreated
* Last modified - d.lastModified
* Region - d.attributes.region
* Account - d.attributes.account

Column 2
* Repo - d.attributes.props.git_repo
* Branch - d.attributes.props.git_branch

Column 3
* CF S3 - d.attributes.props.cf_s3_dir+/ + d.attributes.props.cf_s3_name
* CF Aliases - d.attributes.props.cf_aliases - CSV format
* CF Cert name - d.attributes.props.cf_cert_name
* BO Gateway address - d.attributes.props.bo_gateway_address
* Config path - d.attributes.props.config_path

Column 4
* Infra - d.attributes.props.infra_name
* Nexus - d.attributes.props.nexus_name
* Site - d.attributes.props.site_name
* Environment - d.attributes.props.environment_name
* Exchange - d.attributes.props.exchange_name

**API** - use GET v1/resources/findAllResources then filter only "type":"INFRASTRUCTURE" and "module":"aws/schema/cloudfront"



