# Database design overview

For detailed database schema, please refer to the [database schema](schemas/schemas.md).

For graphical representation of the database, please refer to the [database overview](schemas/schema.png).

## Tables

### Profiles

Database Type: Document-Oriented NoSQL Database

Reason: Profiles often have varying attributes and can benefit from a flexible schema.

### Posts with sub tables

Database Type: Relational Database for metadata and an Object Storage Service (e.g., Amazon S3) for media content.

Reason: Posts have structured metadata. Media content (photos, videos) can be stored in an object storage service like Amazon S3/Ceph

### Relationships

Database Type: Relational Database

Reason: Posts have structured data. At this stage, it may not make sense (I'm not sure) to use a graph database. But a graph database could potentially be used later.

### Messages

Database Type: Relational Database

Reason: Messages have structured data. At this stage, it may not make sense (I'm not sure) to use NoSQL Database

### Media

Database Type: A combination of Object Storage Service (e.g., Amazon S3/Ceph) for media storage and a metadata database for efficient indexing and retrieval.

Reason:  Media content (photos, videos) can be stored in an object storage service like Amazon S3/Ceph. For indexing and search we can use a search engine like Elasticsearch.
