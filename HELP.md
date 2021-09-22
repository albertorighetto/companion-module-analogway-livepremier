## Analog Way LivePremier and Midra 4K Series module

This module allows you to control all models of Analog Way's LivePremier and Midra 4K live image processing lineup.
At this time it uses the LivePremier's REST API, so it is basically "fire and forget". That means the module just sends commands and doesn't care about execution or feedback. With the REST API system states could be polled from the system, but the traffic would be to much to continuously pull everything and keep in sync.
That means at this time no feedback is provided by the module. The module will be upgraded when Analog Way releases the announced advanced API.

# Configuration

Enter the IPv4 address and port of device.
IPv6 or hostname is not supported yet.

# Custom variables support
In custom commands you can use variables from other modules or custom variables.
For example, you can create a crosspoint defining some custom variables (i.e. screenId, layerId, target, sourceType, sourceId).
Then you need to create some buttons to change the values and finally you can use the custom variables in a custom command, i.e.:

- Address path:
  - /api/tpp/v1/screens/$(internal:custom_screenId)/live-layers/$(internal:custom_layerId)/presets/$(internal:custom_target)/source
- JSON body:
  - {"sourceType": "$(internal:custom_sourceType)", "sourceId":"$(internal:custom_sourceId)"}
