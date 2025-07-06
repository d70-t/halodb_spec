# Glossary

:::{glossary}

block
: A sequence of bytes identified by a hash and subsequently a {term}`CID`. The hash-based identification makes a block effectively *immutable*. Can be exchanged using various protocols. Can be easily cached, because due to the immutability a block can never be cached in an outdated version.

CID
: *content identifier*: a label identifying content (in particular, an {term}`IPLD` block). See also: [IPFS CIDs](https://docs.ipfs.tech/concepts/content-addressing/)

DNSLink
: Reference to (usually) a {term}`CID`, implemented using the Domain Name System (DNS). Commonly used as updatable name for content addressed data. See also [DNSLink Standard](https://dnslink.dev/)

DOI
: A DOI is an identifier of a digital object. It doesn't rely on content verification (as {term}`CID`s do), but instead creates a contractual framework which encourages DOI providers to properly take care of the referenced objects. It's commonly required for scientific publication. See [doi.org](https://www.doi.org/) for general information and [DataCite Docs](https://support.datacite.org/docs/getting-started) for information about DOIs for scientific datasets.

Good Scientific Practice
: Overarching rules which apply to research work. See [](https://doi.org/10.5281/zenodo.14281892)

IPLD
: InterPlanetary Linked Data. Flexible data model and encoding schemes for content addressed storage. See also: [IPLD docs](https://ipld.io/docs/)

landing page
: A website intended as an overview for a given entity. Often: a *dataset landing page*: a page showing a brief overview of a dataset (e.g. [ORCESTRA: BEACH dropsonde Level 4](https://browser.orcestra-campaign.org/#/ds/ipns://latest.orcestra-campaign.org/products/HALO/dropsondes/Level_4/PERCUSION_Level_4.zarr)). See also [DataCite on DOI landing pages](https://support.datacite.org/docs/landing-pages)

Pin
: To keep (and if required fetch) data identified by {term}`CID`. In many cases *pinning* is done recursively (i.e. data referenced by the pinned CID is pinned as well).
:::
