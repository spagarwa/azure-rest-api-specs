# PostgreSQL

> see https://aka.ms/autorest

This is the AutoRest configuration file for Sql.



---
## Getting Started
To build the SDK for PostgreSQL, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information
These are the global settings for the PostgreSQL API.

``` yaml
title: PostgreSQLManagementClient
description: The Microsoft Azure management API provides create, read, update, and delete functionality for Azure PostgreSQL resources including servers, databases, firewall rules, VNET rules, security alert policies, log files and configurations with new business model.
openapi-type: arm
tag: package-2018-06-01
```

### Tag: package-2020-01-01-privatepreview

These settings apply only when `--tag=package-2020-01-01-privatepreview` is specified on the command line.


``` yaml $(tag) == 'package-2020-01-01-privatepreview'
input-file:
- Microsoft.DBforPostgreSQL/preview/2020-01-01-privatepreview/DataEncryptionKeys.json
```

### Tag: package-2018-06-01-privatepreview

These settings apply only when `--tag=package-2018-06-01-privatepreview` is specified on the command line.


``` yaml $(tag) == 'package-2018-06-01-privatepreview'
input-file:
- Microsoft.DBforPostgreSQL/preview/2018-06-01-privatepreview/PrivateEndpointConnections.json
- Microsoft.DBforPostgreSQL/preview/2018-06-01-privatepreview/PrivateLinkResources.json
```

### Tag: package-2018-06-01

These settings apply only when `--tag=package-2018-06-01` is specified on the command line.


``` yaml $(tag) == 'package-2018-06-01'
input-file:
- Microsoft.DBforPostgreSQL/stable/2017-12-01/postgresql.json
- Microsoft.DBforPostgreSQL/stable/2018-06-01/PrivateEndpointConnections.json
- Microsoft.DBforPostgreSQL/stable/2018-06-01/PrivateLinkResources.json
```


### Tag: package-2017-12-01-preview

These settings apply only when `--tag=package-2017-12-01-preview` is specified on the command line.


``` yaml $(tag) == 'package-2017-12-01-preview'
input-file:
- Microsoft.DBforPostgreSQL/preview/2017-12-01-preview/postgresql.json
```

### Tag: package-2017-12-01

These settings apply only when `--tag=package-2017-12-01` is specified on the command line.


``` yaml $(tag) == 'package-2017-12-01'
input-file:
- Microsoft.DBforPostgreSQL/stable/2017-12-01/postgresql.json
```


---
# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-net
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-java
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-node
```

### C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.Management.PostgreSQL
  output-folder: $(csharp-sdks-folder)/postgresql/Microsoft.Azure.Management.PostgreSQL/src/Generated
  clear-output-folder: true
```


## Python

These settings apply only when `--python` is specified on the command line.
Please also specify `--python-sdks-folder=<path to the root directory of your azure-sdk-for-python clone>`.
Use `--python-mode=update` if you already have a setup.py and just want to update the code itself.

``` yaml $(python)
python-mode: create
python:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  payload-flattening-threshold: 2
  namespace: azure.mgmt.rdbms.postgresql
  package-name: azure-mgmt-rdbms
  clear-output-folder: true
```
``` yaml $(python) && $(python-mode) == 'update'
python:
  no-namespace-folders: true
  output-folder: $(python-sdks-folder)/rdbms/azure-mgmt-rdbms/azure/mgmt/rdbms/postgresql
```
``` yaml $(python) && $(python-mode) == 'create'
python:
  basic-setup-py: true
  output-folder: $(python-sdks-folder)/rdbms/azure-mgmt-rdbms
```

## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

See configuration in [readme.java.md](./readme.java.md)

## Multi-API/Profile support for AutoRest v3 generators

AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.

This block is updated by an automatic script. Edits may be lost!

``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../profiles/readme.md

# all the input files across all versions
input-file:
  - $(this-folder)/Microsoft.DBforPostgreSQL/preview/2020-01-01-privatepreview/DataEncryptionKeys.json
  - $(this-folder)/Microsoft.DBforPostgreSQL/preview/2018-06-01-privatepreview/PrivateEndpointConnections.json
  - $(this-folder)/Microsoft.DBforPostgreSQL/preview/2018-06-01-privatepreview/PrivateLinkResources.json
  - $(this-folder)/Microsoft.DBforPostgreSQL/stable/2017-12-01/postgresql.json
  - $(this-folder)/Microsoft.DBforPostgreSQL/stable/2018-06-01/PrivateEndpointConnections.json
  - $(this-folder)/Microsoft.DBforPostgreSQL/stable/2018-06-01/PrivateLinkResources.json
  - $(this-folder)/Microsoft.DBforPostgreSQL/preview/2017-12-01-preview/postgresql.json

```

If there are files that should not be in the `all-api-versions` set,
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file:
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```
