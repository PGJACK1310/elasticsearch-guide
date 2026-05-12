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

## Elasticsearch Indices Query

The following query is used to display all indices available in the Elasticsearch cluster.

```json
GET _cat/indices?v
```
Purpose
- Lists all indices in the Elasticsearch environment.
- Displays index health, status, shard information, and storage details.
- Helps monitor data ingestion and index availability

Query Breakdown
- _cat/indices → Retrieves index information in a human-readable format.
- ?v → Adds column headers for better readability.

Information Displayed
- Health status of indices
- Index name
- Number of primary and replica shards
- Document count
- Storage size
- Index status (open/close)

## CHECK PARTICULER INDEX ACCORDING TO THE NAME 
```json
GET _cat/indices/(INDEX NAME)?v&s=index
```
## Elasticsearch Reindex Query

The following query is used to copy filtered log data from one index to another index in Elasticsearch.

```json
POST _reindex
{
  "source": {
    "index": "example-source-index",
    "query": {
      "match_phrase": {
        "message": "example-keyword"
      }
    }
  },
  "dest": {
    "index": "example-destination-index"
  }
}
```
Purpose
- Copies specific logs from a source index to a destination index.
- Filters logs containing a specific keyword or phrase.
- Used for log segregation and SIEM log management.

Query Breakdown
- POST _reindex → Starts the reindex operation.
- source.index → Original index containing logs.
- match_phrase → Searches for the exact keyword or phrase.
- message → Log field used for filtering.
- dest.index → Destination index where filtered logs are stored.

# Elasticsearch Delete By Query

Deletes documents containing from the `message` field.

## Query

```json
POST /index_name/_delete_by_query?pretty
{
  "query": {
    "match": {
      "message": "message"
    }
  }
}
```
Common Usage
- Separate vendor-specific logs.
- Organize logs into dedicated indices.
- Improve SIEM searching and monitoring.
- Optimize dashboards and detection rules.

# Elasticsearch Cancel Task Example

This Elasticsearch query cancels a running task using the Task Management API.

## Query

```json
POST /_tasks/task_id/_cancel?pretty
```
# Elasticsearch Commands Short Explanation

## Force Merge

```json
POST /_forcemerge?only_expunge_deletes=true
```
## Check Force Merge Tasks
```json
GET /_tasks?detailed=true&actions=*/forcemerge&pretty
```
## Check Delete By Query Tasks
```json
GET /_tasks?detailed=true&actions=*/delete/byquery&pretty
```
