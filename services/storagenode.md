(storagenode)=
# Storage Node / Cluster

A Storage Node (or cluster) stores and distributes IPLD blocks.

* many backends are possible (e.g. filesystem, object store, tape?)
* blocks are accessible via [bitswap](https://specs.ipfs.tech/bitswap-protocol/) and [HTTP trustless gateway](https://specs.ipfs.tech/http-gateways/trustless-gateway/)
* advertises available CIDs using [bitswap](https://specs.ipfs.tech/bitswap-protocol/), [DHT](https://docs.ipfs.tech/concepts/dht/#kademlia) and [IPNI announcements](https://docs.ipfs.tech/concepts/ipni/)
* exposes a pinning service (users can ask the node to keep certain blocks)
  * via [pinning API](https://ipfs.github.io/pinning-services-api-spec/)
  * via HTTP upload of [CAR archives](https://ipld.io/specs/transport/car/carv1/)
  * authenticated by @auth-service
* exposes storage attestation API, a HTTP API answering questions like
  * do you store this CID? -- and it's children?
  * how long will you keep it?
* (TBD / maybe) follows a remote pinlist (e.g. as in [ORCESTRA `pinlist.yaml`](https://github.com/orcestra-campaign/ipfs_tools/blob/main/pinlist.yaml)

## Additional Services

These are likely very useful, but it's likely ok to have fewer replicas of these.

* Network Indexer (tracks, indexes & publishes IPNI updates)
* [Delegated Routing Service](https://specs.ipfs.tech/routing/http-routing-v1/) (exposes routing information from DHT & Network Indexer via HTTP)
* Standalone [HTTP Gateway](https://specs.ipfs.tech/http-gateways/) (maybe less relevant in the longer term, exposes IPFS content via HTTP)

## WPs

* specify requirements for the above mentioned services more thoroughly
* develop quota management (or something that ensures all participants can use the service without becoming unfair)
* specify security recommendations to operate the services in a safe manner
* implement storage node as blueprint for the infrastructure available to project partners
* install & operate such nodes at multiple sites
* install & operate (at least) one network indexer
* install & operate (at least) one delegated routing service
* (TBD / maybe later) develop system for transparent long-term archiving (e.g. Tape connector)
