
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `Anti-virus` | Cisco Secure Web Appliance analyze the content of requests and reponses to prevent malware infection |
| `Web proxy` | Cisco Secure Web Appliance logs provide information about the connected client and the requested resource |
| `Web logs` | Cisco Secure Web Appliance logs provide information about the connected client and the requested resource |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `network`, `web` |
| Type | `connection`, `denied` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "event1.json"

    ```json
	
    {
        "message": "Info: 1649097617.352 7 1.2.3.4 TCP_MISS/302 779 HEAD http://example.g1.com/release2/chrome_component/ncl4aq5sui3jzdal274hizxkxe_102.0.4984.0/jamhcnnkihinmdlkakkaopbjbbcngflc_102.0.4984.0_all_kqe423m2ktlxwrfccq656tbhhi.crx3 - DIRECT/example.g1.com text/html DEFAULT_CASE_12-DefaultGroup-Internal_network-NONE-NONE-NONE-DefaultGroup-NONE <\"IW_infr\",6.8,1,\"-\",-,-,-,-,\"-\",-,-,-,\"-\",-,-,\"-\",\"-\",-,-,\"IW_infr\",-,\"-\",\"Infrastructure and Content Delivery Networks\",\"-\",\"Unknown\",\"Unknown\",\"-\",\"-\",890.29,0,-,\"-\",\"-\",-,\"-\",-,-,\"-\",\"-\",-,-,\"-\",-> - -",
        "event": {
            "start": "2022-04-04T18:40:17.352000Z",
            "duration": 7,
            "kind": "event",
            "category": [
                "web",
                "network"
            ]
        },
        "@timestamp": "2022-04-04T18:40:17.352000Z",
        "observer": {
            "product": "Cisco Web Security Appliances",
            "type": "proxy",
            "vendor": "Cisco"
        },
        "network": {
            "direction": "egress",
            "transport": "tcp"
        },
        "http": {
            "request": {
                "method": "HEAD"
            },
            "response": {
                "status_code": 302,
                "bytes": 779,
                "mime_type": "text/html"
            }
        },
        "url": {
            "original": "http://example.g1.com/release2/chrome_component/ncl4aq5sui3jzdal274hizxkxe_102.0.4984.0/jamhcnnkihinmdlkakkaopbjbbcngflc_102.0.4984.0_all_kqe423m2ktlxwrfccq656tbhhi.crx3",
            "domain": "example.g1.com",
            "top_level_domain": "com",
            "subdomain": "example",
            "registered_domain": "g1.com",
            "path": "/release2/chrome_component/ncl4aq5sui3jzdal274hizxkxe_102.0.4984.0/jamhcnnkihinmdlkakkaopbjbbcngflc_102.0.4984.0_all_kqe423m2ktlxwrfccq656tbhhi.crx3",
            "scheme": "http",
            "port": 80
        },
        "source": {
            "ip": "1.2.3.4",
            "address": "1.2.3.4"
        },
        "destination": {
            "domain": "example.g1.com",
            "address": "example.g1.com",
            "top_level_domain": "com",
            "subdomain": "example",
            "registered_domain": "g1.com"
        },
        "cisco_wsa": {
            "hierarchy_code": "DIRECT",
            "cache_status": "miss",
            "url": {
                "category_code": "IW_infr",
                "category": "Infrastructure and Content Delivery Networks"
            },
            "threat": {
                "name": "-",
                "category": "Not Set"
            }
        },
        "related": {
            "hosts": [
                "example.g1.com"
            ],
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "prefixed.json"

    ```json
	
    {
        "message": "Info: 1278096903.150 97 172.10.11.22 TCP_MISS/200 8187 GET http://my.site.com/ - DIRECT/my.site.com text/plain DEFAULT_CASE_11-PolicyGroupName-Identity-OutboundMalwareScanningPolicy-DataSecurityPolicy-ExternalDLPPolicy-RoutingPolicy <IW_comp,6.9,-,\"-\",-,-,-,-,\"-\",-,-,-,\"-\",-,-,\"-\",\"-\",-,-,IW_comp,-,\"-\",\"-\",\"Unknown\",\"Unknown\",\"-\",\"-\",198.34,0,-,[Local],\"-\",37,\"W32.CiscoTestVector\",33,0,\"WSA-INFECTED-FILE.pdf\",\"fd5ef49d4213e05f448f11ed9c98253d85829614fba368a421d14e64c426da5e\"> -",
        "event": {
            "start": "2010-07-02T18:55:03.150000Z",
            "duration": 97,
            "kind": "event",
            "category": [
                "web",
                "network"
            ]
        },
        "@timestamp": "2010-07-02T18:55:03.150000Z",
        "observer": {
            "product": "Cisco Web Security Appliances",
            "type": "proxy",
            "vendor": "Cisco"
        },
        "network": {
            "direction": "egress",
            "transport": "tcp"
        },
        "http": {
            "request": {
                "method": "GET"
            },
            "response": {
                "status_code": 200,
                "bytes": 8187,
                "mime_type": "text/plain"
            }
        },
        "url": {
            "original": "http://my.site.com/",
            "domain": "my.site.com",
            "top_level_domain": "com",
            "subdomain": "my",
            "registered_domain": "site.com",
            "path": "/",
            "scheme": "http",
            "port": 80
        },
        "rule": {
            "ruleset": "Identity",
            "id": "DEFAULT_CASE_11"
        },
        "source": {
            "ip": "172.10.11.22",
            "address": "172.10.11.22"
        },
        "destination": {
            "domain": "my.site.com",
            "address": "my.site.com",
            "top_level_domain": "com",
            "subdomain": "my",
            "registered_domain": "site.com"
        },
        "file": {
            "name": "WSA-INFECTED-FILE.pdf",
            "hash": {
                "sha256": "fd5ef49d4213e05f448f11ed9c98253d85829614fba368a421d14e64c426da5e"
            }
        },
        "cisco_wsa": {
            "hierarchy_code": "DIRECT",
            "rule": {
                "policy": {
                    "name": "PolicyGroupName",
                    "outbound_malware_scanning": "OutboundMalwareScanningPolicy",
                    "data_security": "DataSecurityPolicy",
                    "external_dlp": "ExternalDLPPolicy",
                    "routing": "RoutingPolicy"
                }
            },
            "cache_status": "miss",
            "url": {
                "category_code": "IW_comp",
                "category": "Computers and Internet"
            },
            "threat": {
                "name": "W32.CiscoTestVector",
                "category_code": 37,
                "reputation_score": 33,
                "category": "Known Malicious and High-Risk Files"
            }
        },
        "related": {
            "hash": [
                "fd5ef49d4213e05f448f11ed9c98253d85829614fba368a421d14e64c426da5e"
            ],
            "hosts": [
                "my.site.com"
            ],
            "ip": [
                "172.10.11.22"
            ]
        }
    }
    	
	```


=== "w3c.json"

    ```json
	
    {
        "message": "1278096903.150 97 172.10.11.22 TCP_MISS/200 8187 GET http://my.site.com/ - DIRECT/my.site.com text/plain DEFAULT_CASE_11-PolicyGroupName-Identity-OutboundMalwareScanningPolicy-DataSecurityPolicy-ExternalDLPPolicy-RoutingPolicy <IW_comp,6.9,-,\"-\",-,-,-,-,\"-\",-,-,-,\"-\",-,-,\"-\",\"-\",-,-,IW_comp,-,\"-\",\"-\",\"Unknown\",\"Unknown\",\"-\",\"-\",198.34,0,-,[Local],\"-\",37,\"W32.CiscoTestVector\",33,0,\"WSA-INFECTED-FILE.pdf\",\"fd5ef49d4213e05f448f11ed9c98253d85829614fba368a421d14e64c426da5e\"> -",
        "event": {
            "start": "2010-07-02T18:55:03.150000Z",
            "duration": 97,
            "kind": "event",
            "category": [
                "web",
                "network"
            ]
        },
        "@timestamp": "2010-07-02T18:55:03.150000Z",
        "observer": {
            "product": "Cisco Web Security Appliances",
            "type": "proxy",
            "vendor": "Cisco"
        },
        "network": {
            "direction": "egress",
            "transport": "tcp"
        },
        "http": {
            "request": {
                "method": "GET"
            },
            "response": {
                "status_code": 200,
                "bytes": 8187,
                "mime_type": "text/plain"
            }
        },
        "url": {
            "original": "http://my.site.com/",
            "domain": "my.site.com",
            "top_level_domain": "com",
            "subdomain": "my",
            "registered_domain": "site.com",
            "path": "/",
            "scheme": "http",
            "port": 80
        },
        "rule": {
            "ruleset": "Identity",
            "id": "DEFAULT_CASE_11"
        },
        "source": {
            "ip": "172.10.11.22",
            "address": "172.10.11.22"
        },
        "destination": {
            "domain": "my.site.com",
            "address": "my.site.com",
            "top_level_domain": "com",
            "subdomain": "my",
            "registered_domain": "site.com"
        },
        "file": {
            "name": "WSA-INFECTED-FILE.pdf",
            "hash": {
                "sha256": "fd5ef49d4213e05f448f11ed9c98253d85829614fba368a421d14e64c426da5e"
            }
        },
        "cisco_wsa": {
            "hierarchy_code": "DIRECT",
            "rule": {
                "policy": {
                    "name": "PolicyGroupName",
                    "outbound_malware_scanning": "OutboundMalwareScanningPolicy",
                    "data_security": "DataSecurityPolicy",
                    "external_dlp": "ExternalDLPPolicy",
                    "routing": "RoutingPolicy"
                }
            },
            "cache_status": "miss",
            "url": {
                "category_code": "IW_comp",
                "category": "Computers and Internet"
            },
            "threat": {
                "name": "W32.CiscoTestVector",
                "category_code": 37,
                "reputation_score": 33,
                "category": "Known Malicious and High-Risk Files"
            }
        },
        "related": {
            "hash": [
                "fd5ef49d4213e05f448f11ed9c98253d85829614fba368a421d14e64c426da5e"
            ],
            "hosts": [
                "my.site.com"
            ],
            "ip": [
                "172.10.11.22"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`cisco_wsa.cache_status` | `keyword` | The Cache status for the given request (can be 'hit', 'miss' or 'denied') |
|`cisco_wsa.hierarchy_code` | `keyword` | The hierarchy used by Cisco Web Security Appliance for this connection. It indicates how the next-hop cache was selected |
|`cisco_wsa.rule.policy.data_security` | `keyword` | The name of the data security policy applied to the request |
|`cisco_wsa.rule.policy.external_dlp` | `keyword` | The name of the external dlp policy applied to the request |
|`cisco_wsa.rule.policy.name` | `keyword` | The name of the policy applied to the request |
|`cisco_wsa.rule.policy.outbound_malware_scanning` | `keyword` | The name of the outbound malware scanning policy applied to the request |
|`cisco_wsa.rule.policy.routing` | `keyword` | The name of the routing policy applied to the request |
|`cisco_wsa.threat.category_code` | `number` | The code of the category of the detected threat |
|`cisco_wsa.threat.name` | `keyword` | The name of the detected threat |
|`cisco_wsa.threat.reputation_score` | `number` | The reputation score from Advanced Malware Protection file scanning |
|`cisco_wsa.url.category_code` | `keyword` | The code of the category of the requested url |
|`destination.domain` | `keyword` | The domain name of the destination. |
|`destination.ip` | `ip` | IP address of the destination. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.duration` | `long` | Duration of the event in nanoseconds. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.start` | `date` | event.start contains the date when the event started or when the activity was first observed. |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`file.hash.sha256` | `keyword` | SHA256 hash. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`http.request.method` | `keyword` | HTTP request method. |
|`http.response.bytes` | `long` | Total size in bytes of the response (body and headers). |
|`http.response.mime_type` | `keyword` | Mime type of the body of the response. |
|`http.response.status_code` | `long` | HTTP response status code. |
|`network.direction` | `keyword` | Direction of the network traffic. |
|`network.transport` | `keyword` | Protocol Name corresponding to the field `iana_number`. |
|`observer.product` | `keyword` | The product name of the observer. |
|`observer.type` | `keyword` | The type of the observer the data is coming from. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`rule.id` | `keyword` | Rule ID |
|`rule.ruleset` | `keyword` | Rule ruleset |
|`source.ip` | `ip` | IP address of the source. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

