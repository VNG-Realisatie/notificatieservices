# Design decisions

## Event attributes

### Overview

All attributes are conform the [GOV NL profile for Cloud Events](https://vng-realisatie.github.io/NL-GOV-profile-for-CloudEvents/) specification unless explicitly stated otherwise.

Attribute           | Remarks
---------           | -----------
id                  | Format MUST be UUID.
source              | Format MUST be URN.
specversion         | Although the version of Cloud Events is implied by the version of the OAS the decision was made to include this attribute in the resource to be fully Cloud Events compatible.
type                | -
datacontenttype     | Value MUST be application/+json
dataschema          | -
~~subject~~         | Not allowed !
time                | -
dataref             | This Cloud Events extension is allowed.
sequence            | This Cloud Events extension is allowed.
sequencetype        | This Cloud Events extension is allowed.
data                | -
data_base64         | As specified in the _JSON Event Format for CloudEvents_.
yana.domain         | See explanation below.
yana.subscriptionId | See explanation below.

### yana.domain


### yana.subscriptionId

