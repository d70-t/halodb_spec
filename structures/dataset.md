(dataset)=
# Dataset

A dataset (for the purpose of the HALO-DB) is characterized as follows:

* A dataset is an IPLD-based tree structure identified by its root CID
  * (this may be, but is not limited to, an immutable folder of a file system)
* There is a (single) function `extract_metadata(CID) -> metadata`, which executes successfully on the root CID
  * (otherwise, what the CID points to is *not* considered a dataset)
* the metadata returned by the function is sufficient to
  * apply for a DOI
  * render a meaningful dataset landing page
  * consider the dataset [FAIR](https://en.wikipedia.org/wiki/FAIR_data)
  * build a search index to reasonably find a specific dataset within a collection of many datasets
* the function `extract_metadata` should be as convenient as possible but must allow to share unknown data types as well
  * a [CF](https://cfconventions.org/) & [ACDD](https://wiki.esipfed.org/Attribute_Convention_for_Data_Discovery_1-3) compliant [Zarr](https://zarr.dev/) dataset must be acceptable without additional metadata
  * we may need a fallback metadata document (e.g. JSON, YAML, etc...) in a root folder to support / describe any other data type (see also [RO-Crate](https://www.researchobject.org/ro-crate/), but maybe something different...)
  * there may be more desired options

## WPs

* specify more thoroughly which kinds of datasets are acceptable
* define the metadata format which is returned by `extract_metadata` (likely [STAC](https://stacspec.org/en)-based)
* implement `extract_metadata` in an open & shareable way (it'll be used in many places)
