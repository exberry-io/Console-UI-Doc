1. Add new item in the menu - `Infrastructure`
2. API - use `GET v1/resources/findAllResources` then filter only `"type":"INFRASTRUCTURE"` and NOT include "module":"aws/schema/cloudfront"
3. Display list with columns:
    1. Name - `d.name`
   <s> b. Type - `d.type` </s>
    2. Resource Name - `d.attributes.resourceName`
    3. Module - `d.attributes.infraInfo.module`
    4. Version - `d.attributes.infraInfo.version`
    5. Last Modified - `d.lastModified`
    6. View - link which displays in a popup the entire info from `d` in JSON format (read-only)
4. Details section below
    1. First created - `d.firstCreated`
    2. Last modified - `d.lastModified`
    3. Region - `d.attributes.region`
    4. Account - `d.attributes.account`
