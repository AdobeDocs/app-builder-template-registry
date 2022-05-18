---
title: Guides - App Builder Template Validation
description: This is the guides overview page of App Builder template validation during submission process
---
# Template Validation

When a template is submitted for review to the App Builder template registry, it goes through a series of validation checks to get verified by Adobe. The tool that performs these checks can be found [here](https://github.com/adobe/aio-lib-template-validation).

## Validation Checks

### package.json

1. The `description` field in the NPM package's `package.json` file must not be empty. Template must have a description.

2. The `keywords` field must contain the keyword `aio-app-builder-template`. 

#### Example

```json
{
  "description": "This is a description."
  "keywords": [
    "keyword1",
    "keyword2",
    "aio-app-builder-template"
  ]
}
```

### install.yml

1. The `categories` field in `install.yml` must not be empty. Template must have categories defined.

2. If the template implements an extension point, `install.yml` should define the `extension` field. It must contain the extension point metadata in the `serviceCode` property. `extension` is an optional property.

3. If the template contains the `services` property to declare the services it uses, `services` must be an array of objects representing a service the template depends on. Each object must contain the `code` property. `services` is an optional property.

#### Example 

```yaml
categories:
  - ui
  - code
services:
  - code: AnalyticsSDK
    credentials: OAuth
  - code: CampaignStandard
extension:
  serviceCode: dx/excshell/1
```