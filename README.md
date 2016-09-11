Consul Based Discovery Plugin for Elasticsearch
======================================

Uses [Consul](https://consul.io) API for Elasticsearch discovery


## Configuration

```
discovery:
  type: consul
  consul:
    service-names: ["CONSUL_SERVICE_NAME1", "CONSUL_SERVICE_NAME2"]
    tag:  OPTIONAL_TAG_TO_FILTER_NODES
    ws-port:  OPTIONAL_TO_SPECIFY_HTTP_API_PORT_FOR_CONSUL_DEFAULT_IS_8500
    ws-host:  OPTIONAL_TO_SPECIFY_HTTP_API_HOST_FOR_CONSUL_DEFAULT_IS_LOCALHOST
    local-ws-port:  DEPRECATED_OPTIONAL_TO_SPECIFY_LOCAL_HTTP_API_PORT_FOR_CONSUL_DEFAULT_IS_8500


```


Key|Example|Description
---|---|---
`discovery.consul.service-names`|`es-dc01-teamA-cluster01-data-nodes`| an array of service names those are registered in consul
`discovery.consul.tag`|`searcher`| **Optional** parameter `tag` to filter nodes registered for given service names, [read more..](https://www.consul.io/docs/agent/services.html)
`discovery.consul.ws-port`|`8500`|**Optional** parameter to specify the port of the consul REST endpoint. **default** value is `8500` [read more...] (https://www.consul.io/docs/agent/options.html#http_port)
`discovery.consul.ws-host`|`localhost`|**Optional** parameter to specify the hostname of the consul REST endpoint. **default** value is `localhost` [read more...] (https://www.consul.io/docs/agent/options.html#_bind)
`discovery.consul.local-ws-port`|`8500`|**Deprecated** parameter to specify the rest web end point's port on localhost for consul. **default** value is `8500` [read more...] (https://www.consul.io/docs/agent/options.html#http_port)

This plugin is based on https://github.com/grantr/elasticsearch-srv-discovery and
modified to be based on consul API calls instead of DNS records.
