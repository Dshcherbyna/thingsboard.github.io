
* TOC
{:toc}

## Entities Overview

ThingsBoard provides the user interface and REST APIs to provision and manage multiple entity types and their relations in your IoT application.
Supported entities are:

 - **[Tenants](/docs/{{docsPrefix}}user-guide/ui/tenants/)** - you can treat the tenant as a separate business-entity: it's an individual or an organization who owns or produce devices and assets;
 Tenant may have multiple tenant administrator users and millions of customers, devices and assets;
 - **[Customers](/docs/{{docsPrefix}}user-guide/ui/customers/)** - the customer is also a separate business-entity: individual or organization who purchase or uses tenant devices and/or assets;
 Customer may have multiple users and millions of devices and/or assets;
 - **[Users](/docs/{{docsPrefix}}user-guide/ui/users/)** - users are able to browse dashboards and manage entities;
 - **[Devices](/docs/{{docsPrefix}}user-guide/ui/devices/)** - basic IoT entities that may produce telemetry data and handle RPC commands. For example, sensors, actuators, switches;
 - **[Assets](/docs/{{docsPrefix}}user-guide/ui/assets/)** - abstract IoT entities that may be related to other devices and assets. For example factory, field, vehicle;
 - **[Entity Views](/docs/{{docsPrefix}}user-guide/entity-views/)** - useful if you like to share only part of device or asset data to the customers;
 - **[Alarms](/docs/{{docsPrefix}}user-guide/alarms/)** - events that identify issues with your assets, devices, or other entities;
 - **[Dashboards](/docs/{{docsPrefix}}user-guide/dashboards/)** - visualization of your IoT data and ability to control particular devices through the user interface;
 - **Rule Node** - processing units for incoming messages, entity lifecycle events, etc;
 - **Rule Chain** - defines the flow of the processing in the [Rule Engine](/docs/{{docsPrefix}}user-guide/rule-engine-2-0/re-getting-started/). May contain many rule nodes and links to other rule chains;

Each entity supports:

 - **[Attributes](/docs/{{docsPrefix}}user-guide/attributes/)** - static and semi-static key-value pairs associated with entities. For example serial number, model, firmware version;
 - **[Time-series data](/docs/{{docsPrefix}}user-guide/telemetry/)** - time-series data points available for storage, querying and visualization. For example temperature, humidity, battery level;
 - **Relations** - directed connections to other entities. For example contains, manages, owns, produces.

Some entities support profiles:

  - **[Tenant Profiles](/docs/{{docsPrefix}}user-guide/tenant-profiles/)** - contains common settings for multiple tenants: entity, API and rate limits, etc. Each Tenant has the one and only profile at a single point in time.
  - **[Device Profiles](/docs/{{docsPrefix}}user-guide/device-profiles/)** - contains common settings for multiple devices: processing and transport configuration, etc. Each Device has the one and only profile at a single point in time.

{% if docsPrefix == "pe/" %}
**[Entity Groups](/docs/pe/user-guide/groups/)**:

ThingsBoard Professional Edition allows you to configure Entity Groups for Customers, Users, Devices, Assets, Entity Views and Dashboards.
Each entity may belong to multiple groups simultaneously. Entity Group always have an owner - particular Tenant or Customer.
All entities in the group must have the same entity type (i.e. You can't put device and asset into one group).
Entity Groups are useful for dashboards and data processing, but the primary reason of their existence is to support advanced Role-Based Access Control ([RBAC](/docs/pe/user-guide/rbac/)) for IoT.

**[Integrations](/docs/user-guide/integrations/)** and **[Data Converters](/docs/user-guide/integrations/#data-converters)**:

ThingsBoard Platform integrations feature was designed for two primary use cases / deployment options:

  - Connect existing NB IoT, LoRaWAN, SigFox and other devices with specific payload formats directly to ThingsBoard platform.
  - Stream data from devices connected to existing IoT Platforms to enable real-time interactive dashboards and efficient data processing.

Data Converters is a part of the Platform Integrations feature. Their purpose is to transform raw payload from device to the format that ThingsBoard uses and vise-versa.

{% endif %}

This guide provides an overview of the features listed above, some useful links to get more details, and real-life examples of their usage.

## Real-life application

The easiest way to understand the concepts of ThingsBoard is to implement your first ThingsBoard application.
Let's assume we want to build an application that collects data from soil moisture and temperature sensors,
visualize this data on the dashboard, detect issues, raise alarms and control the irrigation.

Let's also assume we want to support multiple fields with hundreds of sensors. Fields may be also grouped into the Geo regions.

We believe there should be the following logical steps to build such an application:

### Step 1: Provision entities and relations

We are going to setup following hierarchy of assets and devices:


 ![image](/images/user-guide/entities-and-relations.svg)


Please review the following soundless screencast to learn **how to provision region and fields assets and their relations using ThingsBoard Web UI**:

<div id="video">
    <div id="video_wrapper">
        <iframe src="https://www.youtube.com/embed/C-JoOfTBeT0" frameborder="0" allowfullscreen></iframe>
    </div>
</div>

Please review the following soundless screencast to learn **how to provision devices and their relations with assets using ThingsBoard Web UI**:


<div id="video">
    <div id="video_wrapper">
        <iframe src="https://www.youtube.com/embed/BUFinxvzIo4" frameborder="0" allowfullscreen></iframe>
    </div>
</div>

**You can automate these actions using ThingsBoard REST API.** You can provision a new asset using a POST request to the following URL

```shell
http(s)://host:port/api/asset
```

For example:

{% capture tabspec %}create-asset
A,create-asset.sh,shell,resources/create-asset.sh,/docs/{{docsPrefix}}user-guide/resources/create-asset.sh
B,create-asset.json,json,resources/create-asset.json,/docs/{{docsPrefix}}user-guide/resources/create-asset.json{% endcapture %}
{% include tabs.html %}

**Note:** in order to execute this request, you will need to substitute **$JWT_TOKEN** with a valid JWT token.
This token should belong to a user with **TENANT_ADMIN** role. You can use following [guide](/docs/{{docsPrefix}}reference/rest-api/#rest-api-auth) to get the token.

Also, you can provision new relation using a POST request to the following URL

```shell
http(s)://host:port/api/relation
```

For example:

{% capture tabspec %}create-relation
A,create-relation.sh,shell,resources/create-relation.sh,/docs/{{docsPrefix}}user-guide/resources/create-relation.sh
B,create-relation.json,json,resources/create-relation.json,/docs/{{docsPrefix}}user-guide/resources/create-relation.json{% endcapture %}
{% include tabs.html %}

**Note:** Don't forget to replace $FROM_ASSET_ID and $TO_ASSET_ID with valid asset ids.

**Note:** One can relate to any entities. For example, assets to devices or assets to users.
You can receive them as a result of a previous REST API call or use Web UI.


### Step 2: Assign attributes to the assets

ThingsBoard provides the ability to assign attributes to entities and manage them.
You are welcome to learn how to do it here:
<p><a href="/docs/{{docsPrefix}}user-guide/attributes" class="button">Working with device attributes</a></p>


### Step 3: Upload telemetry data from devices

ThingsBoard provides the ability to work with telemetry data for devices and other entities.
You are welcome to learn how to do it here:
<p><a href="/docs/{{docsPrefix}}user-guide/telemetry" class="button">Working with telemetry data</a></p>

### Step 4: Creating Rules for Alarms

ThingsBoard provides the ability to raise alarms using rule engine for devices and other entities.
You are welcome to learn how to do it here:
<p><a href="/docs/{{docsPrefix}}user-guide/alarms" class="button">Working with alarms</a></p>

### Step 5: Design your dashboard

Please [import](/docs/{{docsPrefix}}user-guide/ui/dashboards/#dashboard-import) the following [**dashboard**](/docs/{{docsPrefix}}user-guide/resources/region_fields_dashboard.json) that demonstrates Map, Alarm, Entity Table and Charts widgets.
