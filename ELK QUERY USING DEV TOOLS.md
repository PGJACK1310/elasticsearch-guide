## Elasticsearch Dev Tools Query

The following query is used to configure Elasticsearch index settings by setting the replica shard count to `0`.

```json
PUT /_settings
{
  "index": {
    "number_of_replicas": 0
  }
}
```
Purpose
- Disables replica shards for all indices.
- Commonly used in single-node Elastic SIEM environments.
- Resolves unassigned replica shard issues.
- Changes cluster health from Yellow to Green.
- Reduces resource usage and improves indexing performance in lab/testing environments.

## Elasticsearch Cluster Health Query

The following query is used to check the health status of the Elasticsearch cluster.

```json
GET /_cluster/health
```
Purpose
- Retrieves the current cluster health status.
- Displays the status of nodes, shards, and indices.
- Helps monitor Elasticsearch cluster availability and performance.

Cluster Health Status
- Green → All primary and replica shards are allocated.
- Yellow → Primary shards are allocated, but replica shards are unassigned.
- Red → One or more primary shards are missing or unavailable.

Common Usage
- Verify Elasticsearch cluster status after configuration changes.
- Check shard allocation issues in SIEM environments.
- Monitor cluster stability and node availability.
- Troubleshoot indexing or search performance issues.
