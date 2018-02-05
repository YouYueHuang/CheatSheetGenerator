# Kibana

A analytics and visualization platform

```sh
cd kibana-6.1.3/bin
kibana
```

View the cluster health in console of dev tools
```
GET /_cat/health?v
```

List all indices
```
GET /_cat/indices?v
```

Create an index and check
```sh
PUT /customer?pretty
GET /_cat/indices?v
```

Index and query a document
```
PUT /your_index/doc/1?pretty
{
  "feature_1": "feature_1_value"
}
GET /your_index/doc/1?pretty
```

View field mapping
`GET /your_index/_mapping`

Delete index
`DELETE /your_index`

Create index pattern in Management
Index patterns: type index name, configure settings and establish index in Kibana. 

Create visualization in visualize