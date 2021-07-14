---
layout: docwithnav-pe
assignees:
- nick
title: LWM2M Device API Reference
description: Supported LwM2M API Reference for IoT Devices

sysadm-add:
    1:
        image: /images/lwm2m/sysadm-add-pe.png
        title: 'In the Resources library, cLick the "+" sign to add a resource.'
    2:
        image: /images/lwm2m/sysadm-add-1-pe.png
        title: 'Click on the "Drop a resource file or click to select a file to upload" and select ONE xml file (for LWM2M model) and click "Add". '
    3:
        image: /images/lwm2m/sysadm-add-2-pe.png
        title: 'After adding LWM2M model, you are able to download the resource, nevertheless, only system administrator can delete it.'

tenant-add:
    1:
        image: /images/lwm2m/tenant-add-pe.png
    2:
        image: /images/lwm2m/tenant-add-1-pe.png
    3:
        image: /images/lwm2m/tenant-add-2-pe.png
    4:
        image: /images/lwm2m/tenant-add-3-pe.png
    5:
        image: /images/lwm2m/tenant-add-4-pe.png

deviceprofile-objects:
    0:
        image: /images/lwm2m/deviceprofile-objects-pe.png
    1:
        image: /images/lwm2m/deviceprofile-objects-1-pe.png

objects-config:
    0:
        image: /images/lwm2m/objects-config-pe.png
    1:
        image: /images/lwm2m/objects-config-1-pe.png

telemetry-config:
    0:
        image: /images/lwm2m/telemetry-config-pe.png
    1:
        image: /images/lwm2m/telemetry-config-1-pe.png
    2:
        image: /images/lwm2m/telemetry-config-2-pe.png
    3:
        image: /images/lwm2m/telemetry-config-3-pe.png

credentials:
    0:
        image: /images/lwm2m/rpk-pe.png
    1:
        image: /images/lwm2m/spk-pe.png
    2:
        image: /images/lwm2m/x509-pe.png

nosecure:
    0:
        image: /images/lwm2m/nosecur-pe.png

wakaama-terminal:
    0:
        image: /images/lwm2m/wakaama-terminal.png
    1:
        image: /images/lwm2m/wakaama-terminal-1-pe.png

rpc:
    0:
        image: /images/lwm2m/add-rpc-pe.png
        title: 'Enter your dashboard edit mode by clicking the pencil icon in the lower right corner of the screen.'
    1:
        image: /images/lwm2m/add-rpc-1-pe.png
        title: 'To add the new widget either click "Add new widget" sign in the middle of the screen, or the plus sign in the lower right corner of the screen to open the drop-up menu, where
                you can click the paper icon that adds a widget.'
    2:
        image: /images/lwm2m/add-rpc-2-pe.png
        title: 'From the bundle list, select Control widgets.'
    3:
        image: /images/lwm2m/add-rpc-3-pe.png
        title: 'In the Control widgets bundle, choose the RPC debug terminal widget.'
    4:
        image: /images/lwm2m/add-rpc-4-pe.png
        title: 'From the drop-down menu in the Target device field, select configured alias with the target device.'
    5:
        image: /images/lwm2m/add-rpc-5-pe.png
        title: 'To change widget size, pull its edges. When widget size configured, click the orange checkmark in the lower right corner of the screen.'

rpc-command:
    0:
        image: /images/lwm2m/rpc-command-pe.png

---

{% assign docsPrefix = "pe/" %}
{% include docs/reference/lwm2m-api.md %}