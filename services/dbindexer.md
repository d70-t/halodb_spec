(dbindexer)=
# DB-Indexing service

The indexing service takes a collection of @dataset {term}`CID`s (e.g. all CIDs which are considered part of HALO-DB) and creates (or usually updates) the @dbindex. As part of the indexing process, the indexing service uses the `extract_metadata` function (see @dataset) to gather all required metadata.

The indexing service can augment the index with other information. E.g. DOIs issued by the @doiservice, relations between datasets (like updates).

## prior art

* [`scanMetadata.ts`](https://github.com/orcestra-campaign/ipfsui/blob/main/cli/scanMetadata.ts), the script which builds the index of the [ORCESTRA data browser](https://browser.orcestra-campaign.org/)

## WPs

* implement a service which does this indexing for HALO-DB
* optimize the implementation to allow efficient updates
