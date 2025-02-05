> There are existing proxies that have ultra high performance. There are also existing proxies that have a high level of extensibility and dynamic configurability. **The union of performance, extensibility, and dynamic configurability** is what in my opinion makes Envoy so compelling to many.— https://blog.envoyproxy.io/the-universal-data-plane-api-d15cec7a

1. **Dynamic Configuration**: Envoy can be configured dynamically without requiring any restart. We just bootstrap Envoy a configuration and then feed the future configuration with via
   management server.
    - https://www.envoyproxy.io/docs/envoy/latest/api-docs/xds_protocol
3. **Extensibility**: We can develop filter plugins for L4, and L7. We wrote our own L7 filter for Elastic Search, Druid, Solr Database Protocols and L4 filter for MSSQL.Beside that,
   we exensibly use OSS L4/L7 filters like PostgresPorxy, MySQLProxy, KafkaProxy, MongoProxy, RedisProxy, and HCM. To meet our purposes we even do modification to those existing filters. In fact,
   we build an Database Audit tool based on those filters.
5. **Performance**: It provides High throughput, low latency, comsuming little CPU, and RAM
