(dbindex)=
# DB-Index

The database index is the primary search structure of the HALO-DB.
It contains a list of all [datasets](#dataset) which are considered part of the HALO-DB, as well as additional data structures which allow fast lookups.

* The DB-Index is an IPLD-based tree structure identified by its root CID.
* The DB-Index enables clients to quickly search for datasets based on
  * free text
  * keywords
  * (spatial) regions
  * time ranges
  * other (related) datasets
* The DB-Index should support user interfaces describing the data. This may necessitate to cache some or all dataset metadata in the index.
* The DB-Index is versioned
  * It may point to previous versions of itself
  * the latest version is pointed to by a name (e.g. using {term}`DNSLink`)
* There may be multiple indices (e.g. for different applications, special tasks, cross-platform field campaigns)
  * but only *one* is called "HALO-DB"

## WPs

* specify the format of the index datastructure
* specify & implement operations on the index data structure
  * in particular search queries
