# Creating a new dataset

```{mermaid}

flowchart TD
  create["create tree (ipfs add)"] --> valid{"valid dataset?\n (extract_metadata)"}
  create --> pin[pinning service]
  valid -->|no| create
  valid -->|yes| review{"review OK?"}
  review -->|no| create
  review -->|yes| collect["add to HALO-DB CID collection"]
  collect --> index["build DB-index"]
  index --> pin
  index --> update_head["update index-head\n(DNS -> CID link)"]
  collect  --> mk_doi["(optional) create DOI"]
  valid -.->|"yes\n(maybe)"| mk_doi
  mk_doi --> index
```
