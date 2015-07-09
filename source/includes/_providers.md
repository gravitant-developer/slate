# Providers
A cloud provider is a company that offers some component of cloud computing - typically Infrastructure as a Service (IaaS), Software as a Service (SaaS) or Platform as a Service (PaaS) - to other businesses or individuals. Cloud providers are also referred to as cloud service providers or CSPs.

## Search Providers

```shell
curl "http://microservice-api.grav.cm/providers/search/?active=true&page=1&size=5"
```

> The above command returns JSON structured like this:

```json
{
  "page_number": 1,
  "page_size": 10,
  "total_pages": 1,
  "total_count": 3,
  "items": [
    {
      "id": "06146db0-6774-4cba-9fba-820eec42e7a9",
      "name": "helion",
      "active": true,
      "display_name": "HP Helion",
      "description": "HP Helion Public Cloud is a transparent, enterprise-grade public cloud based on OpenStack® technology. Offers on-demand, pay-as-you-go cloud services for computing and storage infrastructure as well as platform services.",
      "thumbnail": "http://res.cloudinary.com/gravitant/image/upload/v1428598729/providers/hphelion.png",
      "deployment_types": [
        "public"
      ],
      "service_types": [
        "iaas"
      ],
      "created_by": "system",
      "modified_by": "system"
    },
    {
      "id": "12fe5d75-902c-492b-82cc-b42eecf3f928",
      "name": "azure",
      "active": true,
      "display_name": "Windows Azure",
      "description": "Windows Azure Cloud Services from Microsoft enables businesses to create highly-available, scalable applications and services using a rich PaaS environment. Supports advanced multi-tier scenarios, automated deployments and elastic scale.",
      "thumbnail": "http://res.cloudinary.com/gravitant/image/upload/v1428597426/providers/azure.jpg",
      "deployment_types": [
        "private"
      ],
      "service_types": [
        "saas"
      ],
      "created_by": "system",
      "modified_by": "system"
    },
    {
      "id": "4aa83114-3133-493d-a1eb-07c54f455118",
      "name": "aws",
      "active": true,
      "display_name": "Amazon Web Services",
      "description": "Amazon Web Services provides a highly reliable, scalable, low-cost infrastructure platform in the cloud that powers hundreds of thousands of enterprise, government and startup customers businesses in 190 countries around the world.",
      "thumbnail": "http://res.cloudinary.com/gravitant/image/upload/v1428597587/providers/amazonaws.jpg",
      "deployment_types": [
        "public",
        "hybrid",
        "private"
      ],
      "service_types": [
        "iaas"
      ],
      "created_by": "system",
      "modified_by": "system"
    }
]
```

### HTTP Request
`GET http://microservice-api.grav.cm/providers/search`

### Request Parameters
The following querystring parameters are optional:

| Param | Description |
|-------|-------------|
| text | A searchable String for locating a service provider
| service | Retrieves providers that matches with the specified service.  Possible values: `paas`, `iaas`, `saas`.
| deployment | Retrieves providers that matches with the specified deployment model. Possible values: 'hybrid', 'public', 'private'
| active | Only show active providers if set to `true`
| page | Page number of providers to be retrieved
| size | Total number of providers to be retrieved

## Get a Provider

```shell
curl "http://microservice-api.grav.cm/providers/12fe5d75-902c-492b-82cc-b42eecf3f928"
```

> The above command returns JSON structured like this:

```json
{
  "id": "12fe5d75-902c-492b-82cc-b42eecf3f928",
  "name": "azure",
  "active": true,
  "display_name": "Windows Azure",
  "description": "Windows Azure Cloud Services from Microsoft enables businesses to create highly-available, scalable applications and services using a rich PaaS environment. Supports advanced multi-tier scenarios, automated deployments and elastic scale.",
  "thumbnail": "http://res.cloudinary.com/gravitant/image/upload/v1428597426/providers/azure.jpg",
  "deployment_types": [
    "private"
  ],
  "service_types": [
    "saas"
  ],
  "created_by": "system",
  "modified_by": "system"
}
```

Look up a particular provider by its unique identifier.

### HTTP Request
`GET http://microservice-api.grav.cm/providers/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The unique identifier of the provider to retrieve

### Errors
| Error | Message |
|--------------|-------------|
| Not Found | Provider is not found |