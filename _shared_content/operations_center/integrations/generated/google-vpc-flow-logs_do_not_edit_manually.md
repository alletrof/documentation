
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Process use of network` | VPC Flow Logs records sample for network flows samples from Google Cloud instances |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `network` |
| Type | `info` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "flow_logs_gke.json"

    ```json
	
    {
        "message": "{\n  \"insertId\": \"1sxgleif1dyxla\",\n  \"jsonPayload\": {\n    \"dest_gke_details\": {\n      \"cluster\": {\n        \"cluster_location\": \"europe-central2-a\",\n        \"cluster_name\": \"cluster-3\"\n      }\n    },\n    \"src_location\": {\n      \"continent\": \"Europe\",\n      \"country\": \"pol\",\n      \"asn\": 15169\n    },\n    \"dest_vpc\": {\n      \"vpc_name\": \"foo\",\n      \"project_id\": \"hazel-aria-348413\",\n      \"subnetwork_name\": \"foo\"\n    },\n    \"start_time\": \"2022-06-03T12:09:42.501046130Z\",\n    \"end_time\": \"2022-06-03T12:09:42.768509812Z\",\n    \"bytes_sent\": \"1872\",\n    \"reporter\": \"DEST\",\n    \"connection\": {\n      \"src_ip\": \"34.118.64.229\",\n      \"dest_port\": 45950,\n      \"dest_ip\": \"10.0.0.4\",\n      \"src_port\": 443,\n      \"protocol\": 6\n    },\n    \"dest_instance\": {\n      \"region\": \"europe-central2\",\n      \"zone\": \"europe-central2-a\",\n      \"vm_name\": \"gke-cluster-3-default-pool-4e355575-tdhx\",\n      \"project_id\": \"hazel-aria-348413\"\n    },\n    \"packets_sent\": \"16\"\n  },\n  \"resource\": {\n    \"type\": \"gce_subnetwork\",\n    \"labels\": {\n      \"subnetwork_id\": \"7449846049104218257\",\n      \"subnetwork_name\": \"foo\",\n      \"project_id\": \"hazel-aria-348413\",\n      \"location\": \"europe-central2-a\"\n    }\n  },\n  \"timestamp\": \"2022-06-03T12:09:43.654174991Z\",\n  \"logName\": \"projects/hazel-aria-348413/logs/compute.googleapis.com%2Fvpc_flows\",\n  \"receiveTimestamp\": \"2022-06-03T12:09:43.654174991Z\"\n}",
        "event": {
            "end": "2022-06-03T12:09:42.768509812Z",
            "start": "2022-06-03T12:09:42.501046130Z",
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "network": {
            "bytes": 1872,
            "packets": 16,
            "iana_number": "6",
            "name": "foo"
        },
        "google_vpc_flow_logs": {
            "jsonPayload": {
                "reporter": "DEST",
                "connection": {
                    "protocol": 6
                },
                "dest_vpc": {
                    "vpc_name": "foo"
                },
                "dest_gke_details": {
                    "cluster": {
                        "cluster_location": "europe-central2-a"
                    }
                }
            },
            "resource": {
                "labels": {
                    "subnetwork_id": "7449846049104218257",
                    "subnetwork_name": "foo"
                },
                "type": "gce_subnetwork"
            },
            "insertId": "1sxgleif1dyxla",
            "logName": "projects/hazel-aria-348413/logs/compute.googleapis.com%2Fvpc_flows",
            "receiveTimestamp": "2022-06-03T12:09:43.654174991Z"
        },
        "server": {
            "geo": {
                "name": "europe-central2-a"
            }
        },
        "cloud": {
            "project": {
                "id": "hazel-aria-348413"
            },
            "region": "europe-central2",
            "availability_zone": "europe-central2-a"
        },
        "@timestamp": "2022-06-03T12:09:43.654174991Z",
        "destination": {
            "ip": "10.0.0.4",
            "port": 45950,
            "address": "10.0.0.4"
        },
        "source": {
            "ip": "34.118.64.229",
            "port": 443,
            "as": {
                "number": 15169
            },
            "geo": {
                "continent_name": "Europe",
                "country_iso_code": "POL"
            },
            "address": "34.118.64.229"
        },
        "host": {
            "name": "gke-cluster-3-default-pool-4e355575-tdhx"
        },
        "orchestrator": {
            "cluster": {
                "name": "cluster-3"
            },
            "type": "kubernetes"
        },
        "related": {
            "ip": [
                "10.0.0.4",
                "34.118.64.229"
            ]
        }
    }
    	
	```


=== "flow_logs_gke2.json"

    ```json
	
    {
        "message": "{\n  \"insertId\": \"17aa0kaf4hig5c\",\n  \"jsonPayload\": {\n    \"end_time\": \"2022-06-03T12:09:44.424429165Z\",\n    \"packets_sent\": \"32\",\n    \"src_location\": {\n      \"asn\": 15169,\n      \"country\": \"pol\",\n      \"continent\": \"Europe\"\n    },\n    \"start_time\": \"2022-06-03T12:09:44.421947861Z\",\n    \"dest_vpc\": {\n      \"subnetwork_name\": \"foo\",\n      \"vpc_name\": \"foo\",\n      \"project_id\": \"hazel-aria-348413\"\n    },\n    \"bytes_sent\": \"33792\",\n    \"reporter\": \"DEST\",\n    \"dest_instance\": {\n      \"region\": \"europe-central2\",\n      \"project_id\": \"hazel-aria-348413\",\n      \"vm_name\": \"gke-cluster-3-default-pool-4e355575-k1w8\",\n      \"zone\": \"europe-central2-a\"\n    },\n    \"dest_gke_details\": {\n      \"cluster\": {\n        \"cluster_location\": \"europe-central2-a\",\n        \"cluster_name\": \"cluster-3\"\n      }\n    },\n    \"connection\": {\n      \"protocol\": 6,\n      \"dest_ip\": \"10.0.0.3\",\n      \"src_ip\": \"34.118.64.229\",\n      \"src_port\": 443,\n      \"dest_port\": 41834\n    }\n  },\n  \"resource\": {\n    \"type\": \"gce_subnetwork\",\n    \"labels\": {\n      \"project_id\": \"hazel-aria-348413\",\n      \"subnetwork_name\": \"foo\",\n      \"subnetwork_id\": \"7449846049104218257\",\n      \"location\": \"europe-central2-a\"\n    }\n  },\n  \"timestamp\": \"2022-06-03T12:09:52.418604934Z\",\n  \"logName\": \"projects/hazel-aria-348413/logs/compute.googleapis.com%2Fvpc_flows\",\n  \"receiveTimestamp\": \"2022-06-03T12:09:52.418604934Z\"\n}",
        "event": {
            "end": "2022-06-03T12:09:44.424429165Z",
            "start": "2022-06-03T12:09:44.421947861Z",
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "info"
            ]
        },
        "network": {
            "bytes": 33792,
            "packets": 32,
            "iana_number": "6",
            "name": "foo"
        },
        "google_vpc_flow_logs": {
            "jsonPayload": {
                "reporter": "DEST",
                "connection": {
                    "protocol": 6
                },
                "dest_vpc": {
                    "vpc_name": "foo"
                },
                "dest_gke_details": {
                    "cluster": {
                        "cluster_location": "europe-central2-a"
                    }
                }
            },
            "resource": {
                "labels": {
                    "subnetwork_id": "7449846049104218257",
                    "subnetwork_name": "foo"
                },
                "type": "gce_subnetwork"
            },
            "insertId": "17aa0kaf4hig5c",
            "logName": "projects/hazel-aria-348413/logs/compute.googleapis.com%2Fvpc_flows",
            "receiveTimestamp": "2022-06-03T12:09:52.418604934Z"
        },
        "server": {
            "geo": {
                "name": "europe-central2-a"
            }
        },
        "cloud": {
            "project": {
                "id": "hazel-aria-348413"
            },
            "region": "europe-central2",
            "availability_zone": "europe-central2-a"
        },
        "@timestamp": "2022-06-03T12:09:52.418604934Z",
        "destination": {
            "ip": "10.0.0.3",
            "port": 41834,
            "address": "10.0.0.3"
        },
        "source": {
            "ip": "34.118.64.229",
            "port": 443,
            "as": {
                "number": 15169
            },
            "geo": {
                "continent_name": "Europe",
                "country_iso_code": "POL"
            },
            "address": "34.118.64.229"
        },
        "host": {
            "name": "gke-cluster-3-default-pool-4e355575-k1w8"
        },
        "orchestrator": {
            "cluster": {
                "name": "cluster-3"
            },
            "type": "kubernetes"
        },
        "related": {
            "ip": [
                "10.0.0.3",
                "34.118.64.229"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`cloud.availability_zone` | `keyword` | Availability zone in which this host, resource, or service is located. |
|`cloud.project.id` | `keyword` | The cloud project id. |
|`cloud.region` | `keyword` | Region in which this host, resource, or service is located. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.port` | `long` | Port of the destination. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.end` | `date` | event.end contains the date when the event ended or when the activity was last observed. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.start` | `date` | event.start contains the date when the event started or when the activity was first observed. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`google_vpc_flow_logs.insertId` | `keyword` |  |
|`google_vpc_flow_logs.jsonPayload.connection.protocol` | `number` |  |
|`google_vpc_flow_logs.jsonPayload.dest_gke_details.cluster.cluster_location` | `keyword` |  |
|`google_vpc_flow_logs.jsonPayload.dest_vpc.vpc_name` | `keyword` |  |
|`google_vpc_flow_logs.jsonPayload.reporter` | `keyword` |  |
|`google_vpc_flow_logs.logName` | `keyword` |  |
|`google_vpc_flow_logs.receiveTimestamp` | `keyword` |  |
|`google_vpc_flow_logs.resource.labels.subnetwork_id` | `keyword` |  |
|`google_vpc_flow_logs.resource.labels.subnetwork_name` | `keyword` |  |
|`google_vpc_flow_logs.resource.type` | `keyword` |  |
|`host.name` | `keyword` | Name of the host. |
|`network.bytes` | `long` | Total bytes transferred in both directions. |
|`network.iana_number` | `keyword` | IANA Protocol Number. |
|`network.name` | `keyword` | Name given by operators to sections of their network. |
|`network.packets` | `long` | Total packets transferred in both directions. |
|`orchestrator.cluster.name` | `keyword` | Name of the cluster. |
|`orchestrator.type` | `keyword` | Orchestrator cluster type (e.g. kubernetes, nomad or cloudfoundry). |
|`server.geo.name` | `keyword` | User-defined description of a location. |
|`source.as.number` | `long` | Unique number allocated to the autonomous system. |
|`source.geo.continent_name` | `keyword` | Name of the continent. |
|`source.geo.country_iso_code` | `keyword` | Country ISO code. |
|`source.ip` | `ip` | IP address of the source. |
|`source.port` | `long` | Port of the source. |

