# Fetch monthly usage from Unifi controller

The current Unifi Network integration in Home Assistant appears to be missing tracking of monthly WAN usage statistics. We pull this using a REST API call.

Output
```
state_class: total_increasing
isp_name: xxxxxxx
connection_status:
  interface_name: ppp0
  is_active: true
  state: up
  up: true
  uplink_type: wired
unit_of_measurement: GB
device_class: data_size
icon: mdi:wan
friendly_name: Primary WAN
```
```
state_class: total_increasing
isp_name: Unknown ISP
connection_status:
  downtime: 999999
  interface_name: eth7
  is_active: false
  state: down
  up: false
  uplink_type: wired
unit_of_measurement: GB
device_class: data_size
icon: mdi:wan
friendly_name: Failover WAN
```


## Pre-requisite
A Unifi API key is required.

Generate a fresh API key from `Control Panel > Integrations` or re-use existing API key.


## Configuration

### 1. REST.yaml
Place `rest.yaml` file in `config/` alongside rest of your yaml files.

* Configure your API key in your secrets.yaml file
* If you do not have or do not want to use secrets.yaml, directly set the key in `rest.yaml` file.

e.g (include quotes):
```
UDM_API_KEY="12345678"
```

### 2. Place `template.yaml` file or copy code to wherever you are maintaining sensor configuration

### 3. Use your new sensors in dashboard in whatever way you prefer
