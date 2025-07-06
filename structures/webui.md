(webui)=
# Web UI

A web-based interface to assist people in using the other data structures & services.

* It's a (likely single-page) web application, deployable to IPFS / IPLD. It doesn't have it's own APIs, but rather uses the ones provided by the other services.
* The read path *must* be entirely static, i.e. it only accesses other data structures directly (but no service APIs). In consequence, the entire read-portion of the UI can run offline *if* the required {term}`IPLD` {term}`block`s are locally cached. If not all blocks are locally cached, they have to be retrieved from somewhere (usually from any @storagenode).
* Provides a user interface for read workflows:
  * search datasets
  * navigate between datasets
  * summarize contents (i.e. a {term}`landing page`)
  * show usage instructions
  * (maybe) create "download" options
  * enhance datasets with auxiliary information, i.e. information not part of the {term}`CID`. (updates, related datasets, policies, {term}`DOI` availability)
* Provides a user interface for *write* workflows:
  * implements tree creation (e.g. `ipfs add` as a drag & drop tool)
  * implements interaction with @auth-service
  * implements remote pinning at storage node: instruct one or more storage node(s) to {term}`pin` CIDs (created in UI or elsewhere) as currently authenticated user, inform the user about the progress of pinning
  * validates [datasets](#dataset) client-side: `extract_metadata` is succesful (including before any remote pinning)
    * provide fast feedback about formal quality, FAIR compliance etc...
    * provide assistance to improve dataset to make it acceptable
    * provide "soft" feedback: render landing page as early as possible to visualize how the provided metadata will turn out when data is fully published
  * initiates the review process

## prior art

* [ORCESTRA browser](https://browser.orcestra-campaign.org)
* [IPFS Share](https://share.ipfs.io/)

## WPs

* implement basic @dataset {term}`landing page`
* implement overview page (e.g. listing) with search
* implement search refinement (e.g. property based filtering)
* implement dataset ingestion & validation UI
* implement dataset improvement mode (tutor-like)
* (maybe) offer in-browser edit functionality for simple changes (could be dangerous: we prefer teaching users a better dataset creation workflow than encouraging manual on-the-fly edits)
* implement remote pinning UI
* (maybe) implement review process (we want that eventually, but maybe we don't immediately need a good UI for this)
* deploy user interface continuously to IPFS
