# HALO-DB spec

Specifications for building the next version of the HALO-DB.

The specification distinguishes between **data structures** (usually structures based on IPLD objects) and **services** (computer systems running certain software, usually providing some APIs to users and other services).

As HALO-DB aims to be a utility optimized for distributed read-access to data, the entire state of the HALO-DB is defined in terms of data structures on IPLD.
It is anticipated, that for *read* operations, all required processing can happen client side, and no services (except the distributed storage services) are required.
Thus most services are targeting *write* operations (e.g. when users want to add or update some datasets).
