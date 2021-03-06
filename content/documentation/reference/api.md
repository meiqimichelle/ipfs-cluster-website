+++
title = "REST API"
weight = 10
aliases = [
    "/documentation/developer/api"
]
+++

## REST API Reference

IPFS Cluster peers include an API component which provides HTTP-based access to the peer's functionality. The API attempts to be REST-ful in form and behaviour. It is enabled by default, but it can be disabled by removing its section from the `service.json` configuration file.

<div class="tipbox warning">The following API docs are work in progress and serve only as a quick reference. To play with and see how endpoints are used you can use <code>ipfs-cluster-ctl --enc=json --debug ...</code></div>

<div class="tipbox tip">All the available API endpoints and their parametres and object formats are documented and supported by the <a href="https://godoc.org/github.com/ipfs/ipfs-cluster/api/rest/client">API client</a>.</div>

This table provides a quick summary of methods available:

|Method      |Endpoint              |Comment                          |
|:-----------|:---------------------|:--------------------------------|
|`GET`       |`/id`                 |Cluster peer information         |
|`GET`       |`/version`            |Cluster version|
|`GET`       |`/peers`              |Cluster peers|
|`DELETE`    |`/peers/{peerID}`     |Remove a peer|
|`POST`      |`/add`                |Add content to the cluster|
|`GET`       |`/allocations`        |List of pins and their allocations (pinset)|
|`GET`       |`/allocations/{cid}`  |Show a single pin and its allocations (from the pinset)|
|`GET`       |`/pins`               |Local status of all tracked CIDs|
|`POST`      |`/pins/sync`          |Sync local status from IPFS|
|`GET`       |`/pins/{cid}`         |Local status of single CID|
|`POST`      |`/pins/{cid}`         |Pin a CID|
|`POST`      |`/pins/{ipfs\|ipns\|ipld}/<path>`|Pin using an IPFS path|
|`DELETE`    |`/pins/{cid}`         |Unpin a CID|
|`DELETE`    |`/pins/{ipfs\|ipns\|ipld}/<path>`|Unpin using an IPFS path|
|`POST`      |`/pins/{cid}/sync`    |Sync a CID|
|`POST`      |`/pins/{cid}/recover` |Recover a CID|
|`POST`      |`/pins/recover`       |Recover all pins in the receiving Cluster peer|
|`GET`       |`/health/graph`       |  Get connection graph |
