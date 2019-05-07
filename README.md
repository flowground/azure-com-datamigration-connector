# ![LOGO](logo.png) Azure Data Migration Service Resource Provider **flow**ground Connector

## Description

A generated **flow**ground connector for the Azure Data Migration Service Resource Provider API (version 2018-03-15-preview).

Generated from: https://api.apis.guru/v2/specs/azure.com/datamigration/2018-03-15-preview/swagger.json<br/>
Generated at: 2019-05-07T17:38:04+03:00

## API Description

The Data Migration Service helps people migrate their data from on-premise database servers to Azure, or from older database software to newer software. The service manages one or more workers that are joined to a customer's virtual network, which is assumed to provide connectivity to their databases. To avoid frequent updates to the resource provider, data migration tasks are implemented by the resource provider in a generic way as task resources, each of which has a task type (which identifies the type of work to run), input, and output. The client is responsible for providing appropriate task type and inputs, which will be passed through unexamined to the machines that implement the functionality, and for understanding the output, which is passed back unexamined to the client.

## Authorization

Supported authorization schemes:
- OAuth2

For OAuth 2.0 you need to specify OAuth Client credentials as environment variables in the connector repository:
* `OAUTH_CLIENT_ID` - your OAuth client id
* `OAUTH_CLIENT_SECRET` - your OAuth client secret

## Actions

### Get available resource provider actions (operations)

> Lists all available actions exposed by the Data Migration Service resource provider.

*Tags:* `Standard operation` `GET`

#### Input Parameters
* `api-version` - _required_ - Version of the API

### Check name validity and availability

> This method checks whether a proposed top-level resource name is valid and available.

*Tags:* `Standard operation` `POST`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `api-version` - _required_ - Version of the API
* `location` - _required_ - The Azure region of the operation

### Get resource quotas and usage information

> This method returns region-specific quotas and resource usage information for the Data Migration Service.

*Tags:* `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `location` - _required_ - The Azure region of the operation
* `api-version` - _required_ - Version of the API

### Get services in subscription

> The services resource is the top-level resource that represents the Data Migration Service. This method returns a list of service resources in a subscription.

*Tags:* `Service resource` `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `api-version` - _required_ - Version of the API

### Get supported SKUs

> The skus action returns the list of SKUs that DMS supports.

*Tags:* `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `api-version` - _required_ - Version of the API

### Get services in resource group

> The Services resource is the top-level resource that represents the Data Migration Service. This method returns a list of service resources in a resource group.

*Tags:* `Service resource` `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `api-version` - _required_ - Version of the API

### Delete DMS Service Instance

> The services resource is the top-level resource that represents the Data Migration Service. The DELETE method deletes a service. Any running tasks will be canceled.

*Tags:* `Service resource` `Standard operation` `DELETE`

#### Input Parameters
* `deleteRunningTasks` - _optional_ - Delete the resource even if it contains running tasks
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Get DMS Service Instance

> The services resource is the top-level resource that represents the Data Migration Service. The GET method retrieves information about a service instance.

*Tags:* `Service resource` `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Create or update DMS Service Instance

> The services resource is the top-level resource that represents the Data Migration Service. The PATCH method updates an existing service. This method can change the kind, SKU, and network of the service, but if tasks are currently running (i.e. the service is busy), this will fail with 400 Bad Request ("ServiceIsBusy").

*Tags:* `Service resource` `Standard operation` `PATCH`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Create or update DMS Instance

> The services resource is the top-level resource that represents the Data Migration Service. The PUT method creates a new service or updates an existing one. When a service is updated, existing child resources (i.e. tasks) are unaffected. Services currently support a single kind, "vm", which refers to a VM-based service, although other kinds may be added in the future. This method can change the kind, SKU, and network of the service, but if tasks are currently running (i.e. the service is busy), this will fail with 400 Bad Request ("ServiceIsBusy"). The provider will reply when successful with 200 OK or 201 Created. Long-running operations use the provisioningState property.

*Tags:* `Service resource` `Standard operation` `PUT`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Check nested resource name validity and availability

> This method checks whether a proposed nested resource name is valid and available.

*Tags:* `Custom operation` `POST`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `api-version` - _required_ - Version of the API
* `serviceName` - _required_ - Name of the service

### Check service health status

> The services resource is the top-level resource that represents the Data Migration Service. This action performs a health check and returns the status of the service and virtual machine size.

*Tags:* `Service resource` `Custom operation` `POST`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Get projects in a service

> The project resource is a nested resource representing a stored migration project. This method returns a list of projects owned by a service resource.

*Tags:* `Project resource` `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Delete project

> The project resource is a nested resource representing a stored migration project. The DELETE method deletes a project.

*Tags:* `Project resource` `Standard operation` `DELETE`

#### Input Parameters
* `deleteRunningTasks` - _optional_ - Delete the resource even if it contains running tasks
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `api-version` - _required_ - Version of the API

### Get project information

> The project resource is a nested resource representing a stored migration project. The GET method retrieves information about a project.

*Tags:* `Project resource` `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `api-version` - _required_ - Version of the API

### Update project

> The project resource is a nested resource representing a stored migration project. The PATCH method updates an existing project.

*Tags:* `Project resource` `Standard operation` `PATCH`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `api-version` - _required_ - Version of the API

### Create or update project

> The project resource is a nested resource representing a stored migration project. The PUT method creates a new project or updates an existing one.

*Tags:* `Project resource` `Standard operation` `PUT`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `api-version` - _required_ - Version of the API

### Get tasks in a service

> The services resource is the top-level resource that represents the Data Migration Service. This method returns a list of tasks owned by a service resource. Some tasks may have a status of Unknown, which indicates that an error occurred while querying the status of that task.

*Tags:* `Service resource` `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `api-version` - _required_ - Version of the API
* `taskType` - _optional_ - Filter tasks by task type

### Delete task

> The tasks resource is a nested, proxy-only resource representing work performed by a DMS instance. The DELETE method deletes a task, canceling it first if it's running.

*Tags:* `Task resource` `Standard operation` `DELETE`

#### Input Parameters
* `deleteRunningTasks` - _optional_ - Delete the resource even if it contains running tasks
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `taskName` - _required_ - Name of the Task
* `api-version` - _required_ - Version of the API

### Get task information

> The tasks resource is a nested, proxy-only resource representing work performed by a DMS instance. The GET method retrieves information about a task.

*Tags:* `Task resource` `Standard operation` `GET`

#### Input Parameters
* `$expand` - _optional_ - Expand the response
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `taskName` - _required_ - Name of the Task
* `api-version` - _required_ - Version of the API

### Create or update task

> The tasks resource is a nested, proxy-only resource representing work performed by a DMS instance. The PATCH method updates an existing task, but since tasks have no mutable custom properties, there is little reason to do so.

*Tags:* `Task resource` `Standard operation` `PATCH`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `taskName` - _required_ - Name of the Task
* `api-version` - _required_ - Version of the API

### Create or update task

> The tasks resource is a nested, proxy-only resource representing work performed by a DMS instance. The PUT method creates a new task or updates an existing one, although since tasks have no mutable custom properties, there is little reason to update an exising one.

*Tags:* `Task resource` `Standard operation` `PUT`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `taskName` - _required_ - Name of the Task
* `api-version` - _required_ - Version of the API

### Cancel a task

> The tasks resource is a nested, proxy-only resource representing work performed by a DMS instance. This method cancels a task if it's currently queued or running.

*Tags:* `Task resource` `Custom operation` `POST`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `projectName` - _required_ - Name of the project
* `taskName` - _required_ - Name of the Task
* `api-version` - _required_ - Version of the API

### Get compatible SKUs

> The services resource is the top-level resource that represents the Data Migration Service. The skus action returns the list of SKUs that a service resource can be updated to.

*Tags:* `Service resource` `Standard operation` `GET`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Start service

> The services resource is the top-level resource that represents the Data Migration Service. This action starts the service and the service can be used for data migration.

*Tags:* `Service resource` `Custom operation` `POST`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

### Stop service

> The services resource is the top-level resource that represents the Data Migration Service. This action stops the service and the service cannot be used for data migration. The service owner won't be billed when the service is stopped.

*Tags:* `Service resource` `Custom operation` `POST`

#### Input Parameters
* `subscriptionId` - _required_ - Identifier of the subscription
* `groupName` - _required_ - Name of the resource group
* `serviceName` - _required_ - Name of the service
* `api-version` - _required_ - Version of the API

## License

**flow**ground :- Telekom iPaaS / azure-com-datamigration-connector<br/>
Copyright © 2019, [Deutsche Telekom AG](https://www.telekom.de)<br/>
contact: flowground@telekom.de

All files of this connector are licensed under the Apache 2.0 License. For details
see the file LICENSE on the toplevel directory.
