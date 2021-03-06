# EventGrid

> see https://aka.ms/autorest

This is the AutoRest configuration file for EventGrid.


Multiple Azure services publish events to Azure Event Grid. This is the configuration file for generating
the Publish API and the schemas for those events. Each Azure service publishing to Azure Event Grid has its own tag OpenAPI specification
that describes the schemas for its events.

This configuration enables packaging all of the above as one EventGrid data plane library.
This enables customers to download one EventGrid data plane library instead of having to install separate packages to get the event schemas for each service.


---
## Getting Started
To build the SDK for EventGrid, simply [Install AutoRest](https://aka.ms/autorest/install) and in this folder, run:

> `autorest`

To see additional help and options, run:

> `autorest --help`
---

## Configuration



### Basic Information
These are the global settings for the EventGrid API.

``` yaml
title: EventGridClient
description: EventGrid Client
openapi-type: data-plane
tag: package-2018-01
```

### Tag: package-2018-01

These settings apply only when `--tag=package-2018-01` is specified on the command line.

``` yaml $(tag) == 'package-2018-01'
input-file:
- Microsoft.Storage/stable/2018-01-01/Storage.json
- Microsoft.EventHub/stable/2018-01-01/EventHub.json
- Microsoft.Resources/stable/2018-01-01/Resources.json
- Microsoft.EventGrid/stable/2018-01-01/EventGrid.json
- Microsoft.Devices/stable/2018-01-01/IotHub.json
- Microsoft.ContainerRegistry/stable/2018-01-01/ContainerRegistry.json
- Microsoft.ServiceBus/stable/2018-01-01/ServiceBus.json
- Microsoft.Media/stable/2018-01-01/MediaServices.json
- Microsoft.Maps/stable/2018-01-01/Maps.json
- Microsoft.AppConfiguration/stable/2018-01-01/AppConfiguration.json
- Microsoft.SignalRService/stable/2018-01-01/SignalRService.json
- Microsoft.KeyVault/stable/2018-01-01/KeyVault.json
- Microsoft.MachineLearningServices/stable/2018-01-01/MachineLearningServices.json
- Microsoft.Cache/stable/2018-01-01/RedisCache.json
```

---
# Code Generation


## Swagger to SDK

This section describes what SDK should be generated by the automatic system.
This is not used by Autorest itself.

``` yaml $(swagger-to-sdk)
swagger-to-sdk:
  - repo: azure-sdk-for-go
  - repo: azure-sdk-for-python
  - repo: azure-sdk-for-js
  - repo: azure-sdk-for-node
  - repo: azure-sdk-for-ruby
    after_scripts:
      - bundle install && rake arm:regen_all_profiles['azure_event_grid']
```

## C#

These settings apply only when `--csharp` is specified on the command line.
Please also specify `--csharp-sdks-folder=<path to "SDKs" directory of your azure-sdk-for-net clone>`.

``` yaml $(csharp)
csharp:
  azure-arm: true
  license-header: MICROSOFT_MIT_NO_VERSION
  namespace: Microsoft.Azure.EventGrid
  sync-methods: None
  output-folder: $(csharp-sdks-folder)/eventgrid/Microsoft.Azure.EventGrid/src/Generated
  clear-output-folder: true
```


## Go

See configuration in [readme.go.md](./readme.go.md)

## Java

These settings apply only when `--java` is specified on the command line.
Please also specify `--azure-libraries-for-java-folder=<path to the root directory of your azure-libraries-for-java clone>`.

``` yaml $(java)
azure-arm: true
namespace: com.microsoft.azure.eventgrid
license-header: MICROSOFT_MIT_NO_CODEGEN
payload-flattening-threshold: 1
output-folder: $(azure-libraries-for-java-folder)/eventgrid/data-plane
```

## Multi-API/Profile support for AutoRest v3 generators 

AutoRest V3 generators require the use of `--tag=all-api-versions` to select api files.

This block is updated by an automatic script. Edits may be lost!

``` yaml $(tag) == 'all-api-versions' /* autogenerated */
# include the azure profile definitions from the standard location
require: $(this-folder)/../../../profiles/readme.md

# all the input files across all versions
input-file:
  - $(this-folder)/Microsoft.Storage/stable/2018-01-01/Storage.json
  - $(this-folder)/Microsoft.EventHub/stable/2018-01-01/EventHub.json
  - $(this-folder)/Microsoft.Resources/stable/2018-01-01/Resources.json
  - $(this-folder)/Microsoft.EventGrid/stable/2018-01-01/EventGrid.json
  - $(this-folder)/Microsoft.Devices/stable/2018-01-01/IotHub.json
  - $(this-folder)/Microsoft.ContainerRegistry/stable/2018-01-01/ContainerRegistry.json
  - $(this-folder)/Microsoft.ServiceBus/stable/2018-01-01/ServiceBus.json
  - $(this-folder)/Microsoft.Media/stable/2018-01-01/MediaServices.json
  - $(this-folder)/Microsoft.Maps/stable/2018-01-01/Maps.json
  - $(this-folder)/Microsoft.AppConfiguration/stable/2018-01-01/AppConfiguration.json
  - $(this-folder)/Microsoft.SignalRService/stable/2018-01-01/SignalRService.json
  - $(this-folder)/Microsoft.KeyVault/stable/2018-01-01/KeyVault.json
  - $(this-folder)/Microsoft.MachineLearningServices/stable/2018-01-01/MachineLearningServices.json
  - $(this-folder)/Microsoft.Cache/stable/2018-01-01/RedisCache.json

```

If there are files that should not be in the `all-api-versions` set, 
uncomment the  `exclude-file` section below and add the file paths.

``` yaml $(tag) == 'all-api-versions'
#exclude-file: 
#  - $(this-folder)/Microsoft.Example/stable/2010-01-01/somefile.json
```

