---
layout: docwithnav
assignees:
- ashvayka
title: Entities and relations
description: IoT asset management using ThingsBoard entities and relations feature

---

* TOC
{:toc}

## Entities Overview

ThingsBoard provides the user interface and REST APIs to provision and manage multiple entity types, and their relations in your IoT application.
Supported entities are:
 
 - **Tenants** - a tenant is a separate business-entity: it's an individual or an organization who owns or produce devices and assets;
 Tenant can have multiple tenant administrator users and millions of customers;
 - **Customers** - a customer can be also a separate business-entity, but in contradistinction to tenants, they are individual or organization who purchase or uses tenant devices and/or assets;
 Customer can have multiple users and millions of devices and/or assets;
 - **Users** - users are able to view dashboards and manage entities;
 - **Devices** - basic IoT entities that can produce telemetry data and handle RPC commands. For example, sensors, actuators, switches;
 - **Assets** - IoT entities that can be related to other devices and assets. Example of assets are factory, field, vehicle;      
 - **Alarms** - events that identify issues with your assets, devices, or other entities;
 - **Dashboards** - a visualization of your IoT data and ability to control specific devices through the user interface; 
 - **Rule Node** - processing units for incoming messages, entity lifecycle events, etc;
 - **Rule Chain** - a logic unit of related Rule Nodes.


Each entity supports:

 - **Attributes** - static and semi-static key-value pairs associated with entities. Examples of Attributes are serial number, model, firmware version. 
   Attributes can be used in Rule Engine components: filters, processors, and actions;
 - **Telemetry data** - it's time series data points available for storage, querying, and visualization during the given time frame. Telemetry data is used to track change over time. 
   For example, temperature, humidity, battery level;
 - **Relations** - directed connections to other entities. It is possible to configure needed relations with particular Assets. 
   Relations among Assets can be such as "contains", "manages", "owns", or "produces".

Moreover, devices and assets also have their own types. This allows distinguishing them and process data from them differently.
   
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
 
This is the step-by-step guide on **how to provision region and fields assets and their relations using ThingsBoard Web UI:**
1. Go to the Assets section of the menu;
2. Click on the "+" sign ("Add new Asset") at the bottom right of the screen;
3. Input the name "Region A" and type "region" in the Asset Type line. Click "Add";
4. Again, click on the "+" sign at the bottom right of the screen;
5. Type the name "Field A" and type "field" in the Asset Type line. Click "Add";
6. Now, let's create one more Asset, therefore, repeat Step 2.
7. Input the name "Field B" and type "field" in the Asset Type line. Click "Add";
8. The next step is to click on the created Asset "Region A";
9. In the opened window, you shall go to the Relations cell;
10. In the opened Relations segment, click on the grey "+" sign (Add) at the top right of the screen;
11. In the opened window "Add Relations", you can see that the Relations Type is Contains, so you should choose "Asset" from the drop-down Type's menu;
12. Now, choose the Asset you need. In our example it's "Field A". Click "Add";
13. Repeat the 11th Step;
14. This time input "Field B" in the Asset. Click "Add";
15. Close the "Region A" Asset details by clicking on the grey cross icon at the top right of the screen;
16. After that, you shall go to the "Field A" Asset details by clicking on the eponymous box;
17. In the opened "Field A" window in the Relations section, open the drop-down Direction menu;
18. Select "To" instead of "From" in the drop-down Direction menu;
19. Close the "Field A" Asset details by clicking on the grey cross icon at the top right of the screen.



Also, you can watch the following soundless screencast to learn **how to provision region and fields assets and their relations using ThingsBoard Web UI**:
    

  
<div id="video">
    <div id="video_wrapper">
        <iframe src="https://www.youtube.com/embed/C-JoOfTBeT0" frameborder="0" allowfullscreen></iframe>
    </div>
</div>

This is the step-by-step guide on **how to provision devices and their relations with assets using ThingsBoard Web UI**:
1. After we created Relations among Assets, let's go to the Devices section of the menu;
2. Click on the orange "+" sign (Add New Device);
3. In the opened "Add Device" window, type "Sensor A" in the name line;
4. Then, input "moister-temperature" in the Device Type. Click "Add";
5. Repeat the 2nd Step;
6. Now, in the name line, type "Sensor B" and choose already created "moister-temperature" Device type;
7. Again, repeat the 2nd Step;
8. This time in the name line, type "System A" and input "irrigation" in the Device Type line;
9. Go to the Assets section from the main menu on the left of the screen, where you should have had already created Assets "Field A", "Field B", and "Region A";
10. Click on the "Field A" and in the opened window go to the Relations cell;
11. Click on the grey "+" sign on the right of the screen;
12. In the opened "Add Relations" window, leave the Relation type "Contains" as it is, and choose Type og Entity "Device";
13. Then from the drop-down list of the Device's names choose "Sensor A". Click "Add";
14. Repeat the 11th Step, then repeat the 12th Step;
15. Now, from the drop-down list of the Device's names choose "Sensor B". Click "Add;
16. Repeat the 11th Step, then repeat the 12th Step;
17. This time, from the drop-down list of the Device's names choose "System A". Click "Add;
18. Close the "Field A" Asset details by clicking on the grey cross at the top right of the screen;
19. Let's go back to the Devices section, and click on "Sensor A" box;
20. In the "Sensor A" Device details, click on the Relations cell;
21. Select "To" instead of "From" in the Direction menu.

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
A,create-asset.sh,shell,resources/create-asset.sh,/docs/user-guide/resources/create-asset.sh
B,create-asset.json,json,resources/create-asset.json,/docs/user-guide/resources/create-asset.json{% endcapture %}  
{% include tabs.html %}

**Note:** in order to execute this request, you will need to substitute **$JWT_TOKEN** with a valid JWT token.
This token should belong to a user with **TENANT_ADMIN** role. You can use following [guide](/docs/reference/rest-api/#rest-api-auth) to get the token.

Also, you can provision new relation using a POST request to the following URL

```shell 
http(s)://host:port/api/relation
```

For example:

{% capture tabspec %}create-relation
A,create-relation.sh,shell,resources/create-relation.sh,/docs/user-guide/resources/create-relation.sh
B,create-relation.json,json,resources/create-relation.json,/docs/user-guide/resources/create-relation.json{% endcapture %}  
{% include tabs.html %}

**Note:** Don't forget to replace $FROM_ASSET_ID and $TO_ASSET_ID with valid asset ids. 
   
**Note:** One can relate to any entities. For example, assets to devices or assets to users.
You can receive them as a result of a previous REST API call or use Web UI.


### Step 2: Assign attributes to the assets

ThingsBoard provides the ability to assign attributes to entities and manage them.
You are welcome to learn how to do it here:  
<p><a href="/docs/user-guide/attributes" class="button">Working with device attributes</a></p>


### Step 3: Upload telemetry data from devices

ThingsBoard provides the ability to work with telemetry data for devices and other entities.
You are welcome to learn how to do it here:
<p><a href="/docs/user-guide/telemetry" class="button">Working with telemetry data</a></p>

### Step 4: Creating Rules for Alarms

ThingsBoard provides the ability to raise alarms using rule engine for devices and other entities.
You are welcome to learn how to do it here:
<p><a href="/docs/user-guide/alarms" class="button">Working with alarms</a></p>

### Step 5: Design your dashboard

Please [import](/docs/user-guide/ui/dashboards/#dashboard-import) the following [**dashboard**](/docs/user-guide/resources/region_fields_dashboard.json) that demonstrates Map, Alarm, Entity Table and Charts widgets.


 


 
    
