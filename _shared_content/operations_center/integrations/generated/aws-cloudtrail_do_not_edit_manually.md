
## Event Categories


The following table lists the data source offered by this integration.

| Data Source | Description                          |
| ----------- | ------------------------------------ |
| `AWS CloudTrail logs` | Cloudtrail events are analyzed in detail |
| `Services` | CloudTrail logs activities from all AWS Services |





In details, the following table denotes the type of events produced by this integration.

| Name | Values |
| ---- | ------ |
| Kind | `event` |
| Category | `authentication`, `iam`, `network` |
| Type | `access`, `change` |




## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "7602ff70-7e5f-42e9-86b2-36803df39183.json"

    ```json
	
    {
        "message": "{\"eventVersion\":\"1.08\",\"userIdentity\":{\"type\":\"Root\",\"principalId\":\"1111111111\",\"arn\":\"arn:aws:iam::1111111111:root\",\"accountId\":\"1111111111\",\"accessKeyId\":\"ASIA1111111111111\",\"sessionContext\":{\"sessionIssuer\":{},\"webIdFederationData\":{},\"attributes\":{\"creationDate\":\"2022-08-31T07:20:10Z\",\"mfaAuthenticated\":\"true\"}}},\"eventTime\":\"2022-08-31T09:48:47Z\",\"eventSource\":\"ec2.amazonaws.com\",\"eventName\":\"ModifyInstanceAttribute\",\"awsRegion\":\"eu-west-3\",\"sourceIPAddress\":\"aws.internal\",\"userAgent\":\"aws.internal\",\"requestParameters\":{\"instanceId\":\"i-00000000000000000\",\"userData\":\"<sensitiveDataRemoved>\"},\"responseElements\":{\"requestId\":\"5fcae0f1-790c-4a86-85aa-0b3fd120e341\",\"_return\":true},\"requestID\":\"5fcae0f1-790c-4a86-85aa-0b3fd120e341\",\"eventID\":\"8311ce18-5d58-40f1-a4b3-a757df7cbe47\",\"readOnly\":false,\"eventType\":\"AwsApiCall\",\"managementEvent\":true,\"recipientAccountId\":\"1111111111\",\"eventCategory\":\"Management\",\"sessionCredentialFromConsole\":\"true\"}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "ModifyInstanceAttribute",
            "provider": "ec2.amazonaws.com"
        },
        "@timestamp": "2022-08-31T09:48:47.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3",
            "account": {
                "id": "1111111111"
            },
            "instance": {
                "id": "i-00000000000000000"
            }
        },
        "action": {
            "type": "AwsApiCall",
            "name": "ModifyInstanceAttribute",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "type": "Root",
                    "principalId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "accountId": "1111111111",
                    "accessKeyId": "ASIA1111111111111",
                    "sessionContext": {
                        "sessionIssuer": {},
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-08-31T07:20:10Z",
                            "mfaAuthenticated": "true"
                        }
                    }
                },
                "requestParameters": {
                    "userData": "<sensitiveDataRemoved>"
                }
            }
        },
        "user_agent": {
            "original": "aws.internal"
        },
        "user": {
            "id": "1111111111"
        },
        "source": {
            "address": "aws.internal",
            "domain": "aws.internal"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.08",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "type": "Root",
                    "principalId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "accountId": "1111111111",
                    "accessKeyId": "ASIA1111111111111",
                    "sessionContext": {
                        "sessionIssuer": {},
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-08-31T07:20:10Z",
                            "mfaAuthenticated": "true"
                        }
                    }
                },
                "request_parameters": {
                    "userData": "<sensitiveDataRemoved>"
                },
                "flattened": {
                    "response_elements": "{\"_return\": true, \"requestId\": \"5fcae0f1-790c-4a86-85aa-0b3fd120e341\"}",
                    "request_parameters": "{\"instanceId\": \"i-00000000000000000\", \"userData\": \"\\u003csensitiveDataRemoved\\u003e\"}"
                }
            }
        },
        "related": {
            "hosts": [
                "aws.internal"
            ]
        }
    }
    	
	```


=== "event_cloudtrail.json"

    ```json
	
    {
        "message": "{\"awsRegion\":\"eu-west-3\",\"eventID\":\"6ffb6978-7b42-47d1-9aa1-1838ec08b514\",\"eventName\":\"LookupEvents\",\"eventSource\":\"cloudtrail.amazonaws.com\",\"eventTime\":\"2020-08-12T12:26:51Z\",\"eventType\":\"AwsApiCall\",\"eventVersion\":\"1.05\",\"readOnly\":true,\"recipientAccountId\":\"1111111111\",\"requestID\":\"5b8387cf-59e8-4e6e-ba6d-5fe417820c13\",\"requestParameters\":{\"eventCategory\":\"insight\",\"maxResults\":50},\"responseElements\":null,\"sourceIPAddress\":\"1.2.3.4\",\"userAgent\":\"console.amazonaws.com\",\"userIdentity\":{\"accessKeyId\":\"ASIA1111111111111\",\"accountId\":\"1111111111\",\"arn\":\"arn:aws:iam::1111111111:root\",\"principalId\":\"1111111111\",\"sessionContext\":{\"attributes\":{\"creationDate\":\"2020-08-12T07:04:40Z\",\"mfaAuthenticated\":\"false\"},\"sessionIssuer\":{},\"webIdFederationData\":{}},\"type\":\"Root\"}}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "LookupEvents",
            "provider": "cloudtrail.amazonaws.com"
        },
        "@timestamp": "2020-08-12T12:26:51.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3",
            "account": {
                "id": "1111111111"
            }
        },
        "action": {
            "type": "AwsApiCall",
            "name": "LookupEvents",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "accessKeyId": "ASIA1111111111111",
                    "accountId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "principalId": "1111111111",
                    "sessionContext": {
                        "attributes": {
                            "creationDate": "2020-08-12T07:04:40Z",
                            "mfaAuthenticated": "false"
                        },
                        "sessionIssuer": {},
                        "webIdFederationData": {}
                    },
                    "type": "Root"
                }
            }
        },
        "user_agent": {
            "original": "console.amazonaws.com"
        },
        "user": {
            "id": "1111111111"
        },
        "source": {
            "address": "1.2.3.4",
            "ip": "1.2.3.4"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.05",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "accessKeyId": "ASIA1111111111111",
                    "accountId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "principalId": "1111111111",
                    "sessionContext": {
                        "attributes": {
                            "creationDate": "2020-08-12T07:04:40Z",
                            "mfaAuthenticated": "false"
                        },
                        "sessionIssuer": {},
                        "webIdFederationData": {}
                    },
                    "type": "Root"
                },
                "flattened": {
                    "request_parameters": "{\"eventCategory\": \"insight\", \"maxResults\": 50}"
                }
            }
        },
        "related": {
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_ec2-error.json"

    ```json
	
    {
        "message": "{\"eventVersion\": \"1.05\", \"userIdentity\": {\"type\": \"Root\", \"principalId\": \"1111111111\", \"arn\": \"arn:aws:iam::1111111111:root\", \"accountId\": \"1111111111\", \"accessKeyId\": \"AKIA1111111111\"}, \"eventTime\": \"2020-09-22T15:05:22Z\", \"eventSource\": \"ec2.amazonaws.com\", \"eventName\": \"CreateInstanceExportTask\", \"awsRegion\": \"eu-west-3\", \"sourceIPAddress\": \"1.2.3.4\", \"userAgent\": \"aws-cli/1.18.87 Python/3.7.3 Linux/4.19.0-6-amd64 botocore/1.17.30\", \"errorCode\": \"Client.AuthFailure\", \"errorMessage\": \"vm-import-export@amazon.com must have WRITE and READ_ACL permission on the S3 bucket.\", \"requestParameters\": {\"instanceId\": \"i-00000000000000\", \"targetEnvironment\": \"vmware\", \"exportToS3\": {\"diskImageFormat\": \"VMDK\", \"containerFormat\": \"ova\", \"s3Bucket\": \"qbo-export-instance-bucket\", \"s3Prefix\": \"vms\"}}, \"responseElements\": null, \"requestID\": \"5d1c2af1-f216-4771-9922-5a032e2826f5\", \"eventID\": \"249e3b13-41d4-4007-8f04-ef4b4f4341ed\", \"eventType\": \"AwsApiCall\", \"recipientAccountId\": \"1111111111\"}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "CreateInstanceExportTask",
            "code": "Client.AuthFailure",
            "reason": "vm-import-export@amazon.com must have WRITE and READ_ACL permission on the S3 bucket.",
            "provider": "ec2.amazonaws.com"
        },
        "@timestamp": "2020-09-22T15:05:22.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3",
            "account": {
                "id": "1111111111"
            },
            "instance": {
                "id": "i-00000000000000"
            }
        },
        "action": {
            "type": "AwsApiCall",
            "name": "CreateInstanceExportTask",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "errorCode": "Client.AuthFailure",
                "errorMessage": "vm-import-export@amazon.com must have WRITE and READ_ACL permission on the S3 bucket.",
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "type": "Root",
                    "principalId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "accountId": "1111111111",
                    "accessKeyId": "AKIA1111111111"
                }
            }
        },
        "user_agent": {
            "original": "aws-cli/1.18.87 Python/3.7.3 Linux/4.19.0-6-amd64 botocore/1.17.30"
        },
        "user": {
            "id": "1111111111"
        },
        "source": {
            "address": "1.2.3.4",
            "ip": "1.2.3.4"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.05",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "type": "Root",
                    "principalId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "accountId": "1111111111",
                    "accessKeyId": "AKIA1111111111"
                },
                "flattened": {
                    "request_parameters": "{\"exportToS3\": {\"containerFormat\": \"ova\", \"diskImageFormat\": \"VMDK\", \"s3Bucket\": \"qbo-export-instance-bucket\", \"s3Prefix\": \"vms\"}, \"instanceId\": \"i-00000000000000\", \"targetEnvironment\": \"vmware\"}"
                }
            }
        },
        "related": {
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_ec2.json"

    ```json
	
    {
        "message": "{\"eventVersion\":\"1.08\",\"userIdentity\":{\"type\":\"Root\",\"principalId\":\"111111111111\",\"arn\":\"arn:aws:iam::111111111111:root\",\"accountId\":\"111111111111\",\"accessKeyId\":\"ASI00000000000000000\",\"sessionContext\":{\"sessionIssuer\":{},\"webIdFederationData\":{},\"attributes\":{\"creationDate\":\"2022-09-01T06:46:50Z\",\"mfaAuthenticated\":\"true\"}}},\"eventTime\":\"2022-09-01T13:09:23Z\",\"eventSource\":\"ec2.amazonaws.com\",\"eventName\":\"ModifyInstanceAttribute\",\"awsRegion\":\"eu-west-3\",\"sourceIPAddress\":\"AWS Internal\",\"userAgent\":\"AWS Internal\",\"requestParameters\":{\"instanceId\":\"i-00000000000000000\",\"userData\":\"<sensitiveDataRemoved>\"},\"responseElements\":{\"requestId\":\"190dc310-2b3e-41bc-ad3f-970f95f24c1b\",\"_return\":true},\"requestID\":\"190dc310-2b3e-41bc-ad3f-970f95f24c1b\",\"eventID\":\"f832abd6-9496-4f3e-9112-796f64b786e3\",\"readOnly\":false,\"eventType\":\"AwsApiCall\",\"managementEvent\":true,\"recipientAccountId\":\"111111111111\",\"eventCategory\":\"Management\",\"sessionCredentialFromConsole\":\"true\"}\n",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "ModifyInstanceAttribute",
            "provider": "ec2.amazonaws.com"
        },
        "@timestamp": "2022-09-01T13:09:23.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3",
            "account": {
                "id": "111111111111"
            },
            "instance": {
                "id": "i-00000000000000000"
            }
        },
        "action": {
            "type": "AwsApiCall",
            "name": "ModifyInstanceAttribute",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "111111111111",
                "userIdentity": {
                    "type": "Root",
                    "principalId": "111111111111",
                    "arn": "arn:aws:iam::111111111111:root",
                    "accountId": "111111111111",
                    "accessKeyId": "ASI00000000000000000",
                    "sessionContext": {
                        "sessionIssuer": {},
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-09-01T06:46:50Z",
                            "mfaAuthenticated": "true"
                        }
                    }
                },
                "requestParameters": {
                    "userData": "<sensitiveDataRemoved>"
                }
            }
        },
        "user_agent": {
            "original": "AWS Internal"
        },
        "user": {
            "id": "111111111111"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.08",
                "recipient_account_id": "111111111111",
                "user_identity": {
                    "type": "Root",
                    "principalId": "111111111111",
                    "arn": "arn:aws:iam::111111111111:root",
                    "accountId": "111111111111",
                    "accessKeyId": "ASI00000000000000000",
                    "sessionContext": {
                        "sessionIssuer": {},
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-09-01T06:46:50Z",
                            "mfaAuthenticated": "true"
                        }
                    }
                },
                "request_parameters": {
                    "userData": "<sensitiveDataRemoved>"
                },
                "flattened": {
                    "response_elements": "{\"_return\": true, \"requestId\": \"190dc310-2b3e-41bc-ad3f-970f95f24c1b\"}",
                    "request_parameters": "{\"instanceId\": \"i-00000000000000000\", \"userData\": \"\\u003csensitiveDataRemoved\\u003e\"}"
                }
            }
        }
    }
    	
	```


=== "event_iam.json"

    ```json
	
    {
        "message": "{\"awsRegion\":\"us-east-1\",\"eventID\":\"76a4c7d1-1f00-4ceb-b7ad-3d355a3515cd\",\"eventName\":\"CreateUser\",\"eventSource\":\"iam.amazonaws.com\",\"eventTime\":\"2020-08-12T12:16:24Z\",\"eventType\":\"AwsApiCall\",\"eventVersion\":\"1.05\",\"recipientAccountId\":\"1111111111\",\"requestID\":\"4ba495c6-03b8-4eb9-a812-95f89835f68c\",\"requestParameters\":{\"userName\":\"user\"},\"responseElements\":{\"user\":{\"arn\":\"arn:aws:iam::1111111111:user/user\",\"createDate\":\"Aug 12, 2020 12:16:24 PM\",\"path\":\"/\",\"userId\":\"AIDA11111111111111\",\"userName\":\"user\"}},\"sourceIPAddress\":\"1.2.3.4\",\"userAgent\":\"aws-cli/1.18.87 Python/3.7.3 Linux/4.19.0-6-amd64 botocore/1.17.30\",\"userIdentity\":{\"accessKeyId\":\"AKIA11111111111111\",\"accountId\":\"1111111111\",\"arn\":\"arn:aws:iam::1111111111:root\",\"principalId\":\"1111111111\",\"type\":\"Root\"}}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "CreateUser",
            "provider": "iam.amazonaws.com"
        },
        "@timestamp": "2020-08-12T12:16:24.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "us-east-1",
            "account": {
                "id": "1111111111"
            }
        },
        "action": {
            "type": "AwsApiCall",
            "name": "CreateUser",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "accessKeyId": "AKIA11111111111111",
                    "accountId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "principalId": "1111111111",
                    "type": "Root"
                }
            }
        },
        "user_agent": {
            "original": "aws-cli/1.18.87 Python/3.7.3 Linux/4.19.0-6-amd64 botocore/1.17.30"
        },
        "user": {
            "id": "1111111111",
            "name": "AIDA11111111111111"
        },
        "source": {
            "address": "1.2.3.4",
            "ip": "1.2.3.4"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.05",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "accessKeyId": "AKIA11111111111111",
                    "accountId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "principalId": "1111111111",
                    "type": "Root"
                },
                "request_parameters": {
                    "userName": "user"
                },
                "response_elements": {
                    "user": {
                        "userName": "user",
                        "arn": "arn:aws:iam::1111111111:user/user"
                    }
                },
                "flattened": {
                    "response_elements": "{\"user\": {\"arn\": \"arn:aws:iam::1111111111:user/user\", \"createDate\": \"Aug 12, 2020 12:16:24 PM\", \"path\": \"/\", \"userId\": \"AIDA11111111111111\", \"userName\": \"user\"}}",
                    "request_parameters": "{\"userName\": \"user\"}"
                }
            }
        },
        "related": {
            "ip": [
                "1.2.3.4"
            ],
            "user": [
                "AIDA11111111111111"
            ]
        }
    }
    	
	```


=== "event_lambda.json"

    ```json
	
    {
        "message": "{\"awsRegion\":\"eu-west-3\",\"eventID\":\"6a957c22-7dd9-4d2e-a9ba-7c869d726293\",\"eventName\":\"Decrypt\",\"eventSource\":\"kms.amazonaws.com\",\"eventTime\":\"2020-08-12T12:48:09Z\",\"eventType\":\"AwsApiCall\",\"eventVersion\":\"1.05\",\"readOnly\":true,\"recipientAccountId\":\"1111111111\",\"requestID\":\"3d03af66-1431-4911-b809-ab08b9bd604a\",\"requestParameters\":{\"encryptionAlgorithm\":\"SYMMETRIC_DEFAULT\",\"encryptionContext\":{\"aws:lambda:FunctionArn\":\"arn:aws:lambda:eu-west-3:1111111111:function:ctstreamer-dev-s3\"}},\"resources\":[{\"ARN\":\"arn:aws:kms:eu-west-3:1111111111:key/14eb3a8a-ffec-4b0e-a6da-e901d5e6ee9c\",\"accountId\":\"1111111111\",\"type\":\"AWS::KMS::Key\"}],\"responseElements\":null,\"sourceIPAddress\":\"1.2.3.4\",\"userAgent\":\"aws-internal/3 aws-sdk-java/1.11.802 Linux/4.14.181-108.257.amzn1.x86_64 OpenJDK_64-Bit_Server_VM/11.0.7+10-LTS java/11.0.7 vendor/Amazon.com_Inc.\",\"userIdentity\":{\"accessKeyId\":\"ASIA11111111111111\",\"accountId\":\"1111111111\",\"arn\":\"arn:aws:sts::1111111111:assumed-role/user/ctstreamer-dev-s3\",\"principalId\":\"AROA11111111111111:ctstreamer-dev-s3\",\"sessionContext\":{\"attributes\":{\"creationDate\":\"2020-08-12T12:03:12Z\",\"mfaAuthenticated\":\"false\"},\"sessionIssuer\":{\"accountId\":\"1111111111\",\"arn\":\"arn:aws:iam::1111111111:role/user\",\"principalId\":\"AROA11111111111111\",\"type\":\"Role\",\"userName\":\"user\"},\"webIdFederationData\":{}},\"type\":\"AssumedRole\"}}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "Decrypt",
            "provider": "kms.amazonaws.com"
        },
        "@timestamp": "2020-08-12T12:48:09.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3",
            "account": {
                "id": "1111111111"
            }
        },
        "action": {
            "type": "AwsApiCall",
            "name": "Decrypt",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "accessKeyId": "ASIA11111111111111",
                    "accountId": "1111111111",
                    "arn": "arn:aws:sts::1111111111:assumed-role/user/ctstreamer-dev-s3",
                    "principalId": "AROA11111111111111:ctstreamer-dev-s3",
                    "sessionContext": {
                        "attributes": {
                            "creationDate": "2020-08-12T12:03:12Z",
                            "mfaAuthenticated": "false"
                        },
                        "sessionIssuer": {
                            "accountId": "1111111111",
                            "arn": "arn:aws:iam::1111111111:role/user",
                            "principalId": "AROA11111111111111",
                            "type": "Role",
                            "userName": "user"
                        },
                        "webIdFederationData": {}
                    },
                    "type": "AssumedRole"
                },
                "resources": [
                    {
                        "ARN": "arn:aws:kms:eu-west-3:1111111111:key/14eb3a8a-ffec-4b0e-a6da-e901d5e6ee9c",
                        "accountId": "1111111111",
                        "type": "AWS::KMS::Key"
                    }
                ]
            }
        },
        "user_agent": {
            "original": "aws-internal/3 aws-sdk-java/1.11.802 Linux/4.14.181-108.257.amzn1.x86_64 OpenJDK_64-Bit_Server_VM/11.0.7+10-LTS java/11.0.7 vendor/Amazon.com_Inc."
        },
        "user": {
            "id": "1111111111"
        },
        "source": {
            "address": "1.2.3.4",
            "ip": "1.2.3.4"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.05",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "accessKeyId": "ASIA11111111111111",
                    "accountId": "1111111111",
                    "arn": "arn:aws:sts::1111111111:assumed-role/user/ctstreamer-dev-s3",
                    "principalId": "AROA11111111111111:ctstreamer-dev-s3",
                    "sessionContext": {
                        "attributes": {
                            "creationDate": "2020-08-12T12:03:12Z",
                            "mfaAuthenticated": "false"
                        },
                        "sessionIssuer": {
                            "accountId": "1111111111",
                            "arn": "arn:aws:iam::1111111111:role/user",
                            "principalId": "AROA11111111111111",
                            "type": "Role",
                            "userName": "user"
                        },
                        "webIdFederationData": {}
                    },
                    "type": "AssumedRole"
                },
                "resources": [
                    {
                        "ARN": "arn:aws:kms:eu-west-3:1111111111:key/14eb3a8a-ffec-4b0e-a6da-e901d5e6ee9c",
                        "accountId": "1111111111",
                        "type": "AWS::KMS::Key"
                    }
                ],
                "flattened": {
                    "request_parameters": "{\"encryptionAlgorithm\": \"SYMMETRIC_DEFAULT\", \"encryptionContext\": {\"aws:lambda:FunctionArn\": \"arn:aws:lambda:eu-west-3:1111111111:function:ctstreamer-dev-s3\"}}"
                }
            }
        },
        "related": {
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_rds.json"

    ```json
	
    {
        "message": "{\"eventVersion\":\"1.08\",\"userIdentity\":{\"type\":\"Root\",\"principalId\":\"111111111111\",\"arn\":\"arn:aws:iam::111111111111:root\",\"accountId\":\"111111111111\",\"accessKeyId\":\"ASI00000000000000000\",\"sessionContext\":{\"sessionIssuer\":{},\"webIdFederationData\":{},\"attributes\":{\"creationDate\":\"2022-09-01T06:46:50Z\",\"mfaAuthenticated\":\"true\"}}},\"eventTime\":\"2022-09-01T14:13:11Z\",\"eventSource\":\"rds.amazonaws.com\",\"eventName\":\"ModifyDBInstance\",\"awsRegion\":\"eu-west-3\",\"sourceIPAddress\":\"AWS Internal\",\"userAgent\":\"AWS Internal\",\"requestParameters\":{\"dBInstanceIdentifier\":\"database-1\",\"applyImmediately\":true,\"masterUserPassword\":\"****\",\"allowMajorVersionUpgrade\":false,\"maxAllocatedStorage\":1000},\"responseElements\":{\"dBInstanceIdentifier\":\"database-1\",\"dBInstanceClass\":\"db.m6g.large\",\"engine\":\"postgres\",\"dBInstanceStatus\":\"available\",\"masterUsername\":\"postgres\",\"endpoint\":{\"address\":\"x.rds.amazonaws.com\",\"port\":5432,\"hostedZoneId\":\"ZMESEXB7ZGGQ3\"},\"allocatedStorage\":100,\"instanceCreateTime\":\"Sep 1, 2022 12:47:35 PM\",\"preferredBackupWindow\":\"10:10-10:40\",\"backupRetentionPeriod\":7,\"dBSecurityGroups\":[],\"vpcSecurityGroups\":[{\"vpcSecurityGroupId\":\"sg-00000000000000000\",\"status\":\"active\"}],\"dBParameterGroups\":[{\"dBParameterGroupName\":\"default.postgres13\",\"parameterApplyStatus\":\"in-sync\"}],\"availabilityZone\":\"eu-west-3b\",\"dBSubnetGroup\":{\"dBSubnetGroupName\":\"default-vpc-00000000000000000\",\"dBSubnetGroupDescription\":\"Created from the RDS Management Console\",\"vpcId\":\"vpc-00000000000000000\",\"subnetGroupStatus\":\"Complete\",\"subnets\":[{\"subnetIdentifier\":\"subnet-00000000000000000\",\"subnetAvailabilityZone\":{\"name\":\"eu-west-3a\"},\"subnetOutpost\":{},\"subnetStatus\":\"Active\"}]},\"preferredMaintenanceWindow\":\"thu:04:33-thu:05:03\",\"pendingModifiedValues\":{\"masterUserPassword\":\"****\"},\"latestRestorableTime\":\"Sep 1, 2022 2:07:11 PM\",\"multiAZ\":true,\"engineVersion\":\"13.7\",\"autoMinorVersionUpgrade\":true,\"readReplicaDBInstanceIdentifiers\":[],\"licenseModel\":\"postgresql-license\",\"iops\":3000,\"storageThroughput\":0,\"optionGroupMemberships\":[{\"optionGroupName\":\"default:postgres-13\",\"status\":\"in-sync\"}],\"secondaryAvailabilityZone\":\"eu-west-3c\",\"publiclyAccessible\":false,\"storageType\":\"io1\",\"dbInstancePort\":0,\"storageEncrypted\":true,\"kmsKeyId\":\"arn:aws:kms:eu-west-3:111111111111:key/a7dce59f-5b3c-4178-90e1-91103a32b26d\",\"dbiResourceId\":\"db-00000000000000000000000000\",\"cACertificateIdentifier\":\"rds-ca-2019\",\"domainMemberships\":[],\"copyTagsToSnapshot\":true,\"monitoringInterval\":60,\"enhancedMonitoringResourceArn\":\"arn:aws:logs:eu-west-3:111111111111:group:schema:stream:db-00000000000000000000000000\",\"monitoringRoleArn\":\"arn:aws:iam::111111111111:role/role\",\"dBInstanceArn\":\"arn:aws:rds:eu-west-3:111111111111:db:database-1\",\"iAMDatabaseAuthenticationEnabled\":false,\"performanceInsightsEnabled\":true,\"performanceInsightsKMSKeyId\":\"arn:aws:kms:eu-west-3:111111111111:key/a7dce59f-5b3c-4178-90e1-91103a32b26d\",\"performanceInsightsRetentionPeriod\":7,\"deletionProtection\":true,\"associatedRoles\":[],\"httpEndpointEnabled\":false,\"maxAllocatedStorage\":1000,\"tagList\":[],\"customerOwnedIpEnabled\":false,\"networkType\":\"IPV4\",\"backupTarget\":\"region\"},\"requestID\":\"fc070739-07b9-4533-9652-eec872b5ad3d\",\"eventID\":\"eee4217d-4a93-4ad3-89ff-108b25c4c9ab\",\"readOnly\":false,\"eventType\":\"AwsApiCall\",\"managementEvent\":true,\"recipientAccountId\":\"111111111111\",\"eventCategory\":\"Management\",\"sessionCredentialFromConsole\":\"true\"}\n",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "ModifyDBInstance",
            "provider": "rds.amazonaws.com"
        },
        "@timestamp": "2022-09-01T14:13:11.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3",
            "account": {
                "id": "111111111111"
            }
        },
        "action": {
            "type": "AwsApiCall",
            "name": "ModifyDBInstance",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "111111111111",
                "userIdentity": {
                    "type": "Root",
                    "principalId": "111111111111",
                    "arn": "arn:aws:iam::111111111111:root",
                    "accountId": "111111111111",
                    "accessKeyId": "ASI00000000000000000",
                    "sessionContext": {
                        "sessionIssuer": {},
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-09-01T06:46:50Z",
                            "mfaAuthenticated": "true"
                        }
                    }
                },
                "responseElements": {
                    "publiclyAccessible": false
                }
            }
        },
        "user_agent": {
            "original": "AWS Internal"
        },
        "user": {
            "id": "111111111111"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.08",
                "recipient_account_id": "111111111111",
                "user_identity": {
                    "type": "Root",
                    "principalId": "111111111111",
                    "arn": "arn:aws:iam::111111111111:root",
                    "accountId": "111111111111",
                    "accessKeyId": "ASI00000000000000000",
                    "sessionContext": {
                        "sessionIssuer": {},
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-09-01T06:46:50Z",
                            "mfaAuthenticated": "true"
                        }
                    }
                },
                "response_elements": {
                    "publiclyAccessible": false,
                    "pendingModifiedValues": {
                        "masterUserPassword": "****"
                    }
                },
                "flattened": {
                    "response_elements": "{\"allocatedStorage\": 100, \"associatedRoles\": [], \"autoMinorVersionUpgrade\": true, \"availabilityZone\": \"eu-west-3b\", \"backupRetentionPeriod\": 7, \"backupTarget\": \"region\", \"cACertificateIdentifier\": \"rds-ca-2019\", \"copyTagsToSnapshot\": true, \"customerOwnedIpEnabled\": false, \"dBInstanceArn\": \"arn:aws:rds:eu-west-3:111111111111:db:database-1\", \"dBInstanceClass\": \"db.m6g.large\", \"dBInstanceIdentifier\": \"database-1\", \"dBInstanceStatus\": \"available\", \"dBParameterGroups\": [{\"dBParameterGroupName\": \"default.postgres13\", \"parameterApplyStatus\": \"in-sync\"}], \"dBSecurityGroups\": [], \"dBSubnetGroup\": {\"dBSubnetGroupDescription\": \"Created from the RDS Management Console\", \"dBSubnetGroupName\": \"default-vpc-00000000000000000\", \"subnetGroupStatus\": \"Complete\", \"subnets\": [{\"subnetAvailabilityZone\": {\"name\": \"eu-west-3a\"}, \"subnetIdentifier\": \"subnet-00000000000000000\", \"subnetOutpost\": {}, \"subnetStatus\": \"Active\"}], \"vpcId\": \"vpc-00000000000000000\"}, \"dbInstancePort\": 0, \"dbiResourceId\": \"db-00000000000000000000000000\", \"deletionProtection\": true, \"domainMemberships\": [], \"endpoint\": {\"address\": \"x.rds.amazonaws.com\", \"hostedZoneId\": \"ZMESEXB7ZGGQ3\", \"port\": 5432}, \"engine\": \"postgres\", \"engineVersion\": \"13.7\", \"enhancedMonitoringResourceArn\": \"arn:aws:logs:eu-west-3:111111111111:group:schema:stream:db-00000000000000000000000000\", \"httpEndpointEnabled\": false, \"iAMDatabaseAuthenticationEnabled\": false, \"instanceCreateTime\": \"Sep 1, 2022 12:47:35 PM\", \"iops\": 3000, \"kmsKeyId\": \"arn:aws:kms:eu-west-3:111111111111:key/a7dce59f-5b3c-4178-90e1-91103a32b26d\", \"latestRestorableTime\": \"Sep 1, 2022 2:07:11 PM\", \"licenseModel\": \"postgresql-license\", \"masterUsername\": \"postgres\", \"maxAllocatedStorage\": 1000, \"monitoringInterval\": 60, \"monitoringRoleArn\": \"arn:aws:iam::111111111111:role/role\", \"multiAZ\": true, \"networkType\": \"IPV4\", \"optionGroupMemberships\": [{\"optionGroupName\": \"default:postgres-13\", \"status\": \"in-sync\"}], \"pendingModifiedValues\": {\"masterUserPassword\": \"****\"}, \"performanceInsightsEnabled\": true, \"performanceInsightsKMSKeyId\": \"arn:aws:kms:eu-west-3:111111111111:key/a7dce59f-5b3c-4178-90e1-91103a32b26d\", \"performanceInsightsRetentionPeriod\": 7, \"preferredBackupWindow\": \"10:10-10:40\", \"preferredMaintenanceWindow\": \"thu:04:33-thu:05:03\", \"publiclyAccessible\": false, \"readReplicaDBInstanceIdentifiers\": [], \"secondaryAvailabilityZone\": \"eu-west-3c\", \"storageEncrypted\": true, \"storageThroughput\": 0, \"storageType\": \"io1\", \"tagList\": [], \"vpcSecurityGroups\": [{\"status\": \"active\", \"vpcSecurityGroupId\": \"sg-00000000000000000\"}]}",
                    "request_parameters": "{\"allowMajorVersionUpgrade\": false, \"applyImmediately\": true, \"dBInstanceIdentifier\": \"database-1\", \"masterUserPassword\": \"****\", \"maxAllocatedStorage\": 1000}"
                }
            }
        }
    }
    	
	```


=== "event_s3.json"

    ```json
	
    {
        "message": "{\"awsRegion\":\"eu-west-3\",\"eventID\":\"bcf6f457-76bc-4e8c-8a7b-8a2451481675\",\"eventName\":\"AssumeRole\",\"eventSource\":\"sts.amazonaws.com\",\"eventTime\":\"2020-08-12T12:03:12Z\",\"eventType\":\"AwsApiCall\",\"eventVersion\":\"1.05\",\"recipientAccountId\":\"1111111111\",\"requestID\":\"34c3d58a-83f5-42cc-9e4d-1beeb85f809c\",\"requestParameters\":{\"roleArn\":\"arn:aws:iam::1111111111:role/user\",\"roleSessionName\":\"session-name\"},\"resources\":[{\"ARN\":\"arn:aws:iam::1111111111:role/user\",\"accountId\":\"1111111111\",\"type\":\"AWS::IAM::Role\"}],\"responseElements\":{\"credentials\":{\"accessKeyId\":\"ASIA11111111111111\",\"expiration\":\"Aug 13, 2020, 12:03:12 AM\",\"sessionToken\":\"11111111111111111111111111111111111111111\"}},\"sharedEventID\":\"e0b224e9-a818-452c-87e3-a1d4078bb102\",\"sourceIPAddress\":\"lambda.amazonaws.com\",\"userAgent\":\"lambda.amazonaws.com\",\"userIdentity\":{\"invokedBy\":\"lambda.amazonaws.com\",\"type\":\"AWSService\"}}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "AssumeRole",
            "provider": "sts.amazonaws.com"
        },
        "@timestamp": "2020-08-12T12:03:12.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3"
        },
        "action": {
            "type": "AwsApiCall",
            "name": "AssumeRole",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "invokedBy": "lambda.amazonaws.com",
                    "type": "AWSService"
                },
                "resources": [
                    {
                        "ARN": "arn:aws:iam::1111111111:role/user",
                        "accountId": "1111111111",
                        "type": "AWS::IAM::Role"
                    }
                ]
            }
        },
        "user_agent": {
            "original": "lambda.amazonaws.com"
        },
        "source": {
            "address": "lambda.amazonaws.com",
            "domain": "lambda.amazonaws.com"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.05",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "type": "AWSService"
                },
                "resources": [
                    {
                        "ARN": "arn:aws:iam::1111111111:role/user",
                        "accountId": "1111111111",
                        "type": "AWS::IAM::Role"
                    }
                ],
                "flattened": {
                    "response_elements": "{\"credentials\": {\"accessKeyId\": \"ASIA11111111111111\", \"expiration\": \"Aug 13, 2020, 12:03:12 AM\", \"sessionToken\": \"11111111111111111111111111111111111111111\"}}",
                    "request_parameters": "{\"roleArn\": \"arn:aws:iam::1111111111:role/user\", \"roleSessionName\": \"session-name\"}"
                }
            }
        },
        "related": {
            "hosts": [
                "lambda.amazonaws.com"
            ]
        }
    }
    	
	```


=== "event_signin.json"

    ```json
	
    {
        "message": "{\"additionalEventData\":{\"LoginTo\":\"https://console.aws.amazon.com/billing/home?region=eu-west-3&state=hashArgs%23%2F&isauthcode=true\",\"MFAUsed\":\"No\",\"MobileVersion\":\"No\"},\"awsRegion\":\"us-east-1\",\"eventID\":\"9d4ca355-a7d3-4422-96ae-dbe2c3431609\",\"eventName\":\"ConsoleLogin\",\"eventSource\":\"signin.amazonaws.com\",\"eventTime\":\"2020-08-19T15:33:43Z\",\"eventType\":\"AwsConsoleSignIn\",\"eventVersion\":\"1.05\",\"recipientAccountId\":\"1111111111\",\"requestParameters\":null,\"responseElements\":{\"ConsoleLogin\":\"Success\"},\"sourceIPAddress\":\"1.2.3.4\",\"userAgent\":\"Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0\",\"userIdentity\":{\"accessKeyId\":\"\",\"accountId\":\"1111111111\",\"arn\":\"arn:aws:iam::1111111111:root\",\"principalId\":\"1111111111\",\"type\":\"Root\"}}",
        "event": {
            "kind": "event",
            "category": [
                "authentication"
            ],
            "type": [
                "allowed"
            ],
            "dataset": "cloudtrail",
            "action": "ConsoleLogin",
            "provider": "signin.amazonaws.com"
        },
        "@timestamp": "2020-08-19T15:33:43.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "us-east-1",
            "account": {
                "id": "1111111111"
            }
        },
        "action": {
            "type": "AwsConsoleSignIn",
            "name": "ConsoleLogin",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "accessKeyId": "",
                    "accountId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "principalId": "1111111111",
                    "type": "Root"
                }
            }
        },
        "user_agent": {
            "original": "Mozilla/5.0 (X11; Linux x86_64; rv:68.0) Gecko/20100101 Firefox/68.0"
        },
        "user": {
            "id": "1111111111"
        },
        "source": {
            "address": "1.2.3.4",
            "ip": "1.2.3.4"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.05",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "accessKeyId": "",
                    "accountId": "1111111111",
                    "arn": "arn:aws:iam::1111111111:root",
                    "principalId": "1111111111",
                    "type": "Root"
                },
                "flattened": {
                    "response_elements": "{\"ConsoleLogin\": \"Success\"}"
                }
            }
        },
        "related": {
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```


=== "event_sts.json"

    ```json
	
    {
        "message": "{\"awsRegion\":\"eu-west-3\",\"eventID\":\"bcf6f457-76bc-4e8c-8a7b-8a2451481675\",\"eventName\":\"AssumeRole\",\"eventSource\":\"sts.amazonaws.com\",\"eventTime\":\"2020-08-12T12:03:12Z\",\"eventType\":\"AwsApiCall\",\"eventVersion\":\"1.05\",\"recipientAccountId\":\"1111111111\",\"requestID\":\"34c3d58a-83f5-42cc-9e4d-1beeb85f809c\",\"requestParameters\":{\"roleArn\":\"arn:aws:iam::1111111111:role/user\",\"roleSessionName\":\"session-name\"},\"resources\":[{\"ARN\":\"arn:aws:iam::1111111111:role/user\",\"accountId\":\"1111111111\",\"type\":\"AWS::IAM::Role\"}],\"responseElements\":{\"credentials\":{\"accessKeyId\":\"ASIA11111111111111\",\"expiration\":\"Aug 13, 2020, 12:03:12 AM\",\"sessionToken\":\"1111111111111111111111111111111111111111111111111111111111111111111111111\"}},\"sharedEventID\":\"e0b224e9-a818-452c-87e3-a1d4078bb102\",\"sourceIPAddress\":\"lambda.amazonaws.com\",\"userAgent\":\"lambda.amazonaws.com\",\"userIdentity\":{\"invokedBy\":\"lambda.amazonaws.com\",\"type\":\"AWSService\"}}",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "AssumeRole",
            "provider": "sts.amazonaws.com"
        },
        "@timestamp": "2020-08-12T12:03:12.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3"
        },
        "action": {
            "type": "AwsApiCall",
            "name": "AssumeRole",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "invokedBy": "lambda.amazonaws.com",
                    "type": "AWSService"
                },
                "resources": [
                    {
                        "ARN": "arn:aws:iam::1111111111:role/user",
                        "accountId": "1111111111",
                        "type": "AWS::IAM::Role"
                    }
                ]
            }
        },
        "user_agent": {
            "original": "lambda.amazonaws.com"
        },
        "source": {
            "address": "lambda.amazonaws.com",
            "domain": "lambda.amazonaws.com"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.05",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "type": "AWSService"
                },
                "resources": [
                    {
                        "ARN": "arn:aws:iam::1111111111:role/user",
                        "accountId": "1111111111",
                        "type": "AWS::IAM::Role"
                    }
                ],
                "flattened": {
                    "response_elements": "{\"credentials\": {\"accessKeyId\": \"ASIA11111111111111\", \"expiration\": \"Aug 13, 2020, 12:03:12 AM\", \"sessionToken\": \"1111111111111111111111111111111111111111111111111111111111111111111111111\"}}",
                    "request_parameters": "{\"roleArn\": \"arn:aws:iam::1111111111:role/user\", \"roleSessionName\": \"session-name\"}"
                }
            }
        },
        "related": {
            "hosts": [
                "lambda.amazonaws.com"
            ]
        }
    }
    	
	```


=== "test_insight.json"

    ```json
	
    {
        "message": "{\"eventVersion\":\"1.08\",\"eventTime\":\"2022-09-05T07:45:00Z\",\"awsRegion\":\"eu-west-3\",\"eventID\":\"7a9130fc-ca15-49d9-b4aa-685f7a0c182a\",\"eventType\":\"AwsCloudTrailInsight\",\"recipientAccountId\":\"1111111111\",\"sharedEventID\":\"0a771801-c0cc-406d-a080-219de884f089\",\"insightDetails\":{\"state\":\"End\",\"eventSource\":\"s3.amazonaws.com\",\"eventName\":\"GetBucketPolicy\",\"insightType\":\"ApiErrorRateInsight\",\"errorCode\":\"NoSuchBucketPolicy\",\"insightContext\":{\"statistics\":{\"baseline\":{\"average\":0.0021817492},\"insight\":{\"average\":1.3333333333},\"insightDuration\":3,\"baselineDuration\":10542},\"attributions\":[{\"attribute\":\"userIdentityArn\",\"insight\":[{\"value\":\"arn:aws:iam::1111111111:root\",\"average\":1.3333333333}],\"baseline\":[{\"value\":\"arn:aws:iam::1111111111:root\",\"average\":0.0020868905},{\"value\":\"arn:aws:sts::1111111111:assumed-role/AWSServiceRoleForConfig/AWSConfig-Describe\",\"average\":9.48587e-05}]},{\"attribute\":\"userAgent\",\"insight\":[{\"value\":\"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.204-124.362.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\",\"average\":0.6666666667},{\"value\":\"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.207-126.363.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\",\"average\":0.6666666667}],\"baseline\":[{\"value\":\"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.204-124.362.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\",\"average\":0.0010434453},{\"value\":\"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.207-126.363.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\",\"average\":0.0009485866},{\"value\":\"AWS Internal\",\"average\":0.0001897173}]}]}},\"eventCategory\":\"Insight\"}\n",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "GetBucketPolicy",
            "code": "NoSuchBucketPolicy",
            "provider": "s3.amazonaws.com"
        },
        "@timestamp": "2022-09-05T07:45:00.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-west-3"
        },
        "action": {
            "type": "AwsCloudTrailInsight",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111"
            }
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.08",
                "recipient_account_id": "1111111111",
                "insight_details": {
                    "state": "End",
                    "type": "ApiErrorRateInsight",
                    "context": "{\"attributions\": [{\"attribute\": \"userIdentityArn\", \"baseline\": [{\"average\": 0.0020868905, \"value\": \"arn:aws:iam::1111111111:root\"}, {\"average\": 9.48587e-05, \"value\": \"arn:aws:sts::1111111111:assumed-role/AWSServiceRoleForConfig/AWSConfig-Describe\"}], \"insight\": [{\"average\": 1.3333333333, \"value\": \"arn:aws:iam::1111111111:root\"}]}, {\"attribute\": \"userAgent\", \"baseline\": [{\"average\": 0.0010434453, \"value\": \"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.204-124.362.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\"}, {\"average\": 0.0009485866, \"value\": \"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.207-126.363.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\"}, {\"average\": 0.0001897173, \"value\": \"AWS Internal\"}], \"insight\": [{\"average\": 0.6666666667, \"value\": \"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.204-124.362.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\"}, {\"average\": 0.6666666667, \"value\": \"[S3Console/0.4, aws-internal/3 aws-sdk-java/1.11.1030 Linux/5.4.207-126.363.amzn2int.x86_64 OpenJDK_64-Bit_Server_VM/25.302-b08 java/1.8.0_302 vendor/Oracle_Corporation cfg/retry-mode/standard]\"}]}], \"statistics\": {\"baseline\": {\"average\": 0.0021817492}, \"baselineDuration\": 10542, \"insight\": {\"average\": 1.3333333333}, \"insightDuration\": 3}}"
                }
            }
        }
    }
    	
	```


=== "test_service_event.json"

    ```json
	
    {
        "message": "{\"eventVersion\":\"1.08\",\"userIdentity\":{\"type\":\"AssumedRole\",\"principalId\":\"AR0000000000000000:1111111111111111111111111\",\"arn\":\"arn:aws:sts::1111111111:assumed-role/role/1111111111111111111111111\",\"accountId\":\"1111111111\",\"accessKeyId\":\"AS000000000000000000\",\"sessionContext\":{\"sessionIssuer\":{\"type\":\"Role\",\"principalId\":\"AR0000000000000000\",\"arn\":\"arn:aws:iam::1111111111:role/service-role/username\",\"accountId\":\"1111111111\",\"userName\":\"username\"},\"webIdFederationData\":{},\"attributes\":{\"creationDate\":\"2022-09-09T07:45:14Z\",\"mfaAuthenticated\":\"false\"}}},\"eventTime\":\"2022-09-09T09:17:32Z\",\"eventSource\":\"elasticfilesystem.amazonaws.com\",\"eventName\":\"NewClientConnection\",\"awsRegion\":\"eu-central-1\",\"sourceIPAddress\":\"AWS Internal\",\"userAgent\":\"elasticfilesystem\",\"requestParameters\":null,\"responseElements\":null,\"eventID\":\"6ff7e265-b0b9-42c0-b4b5-ad140a7f1baa\",\"readOnly\":true,\"resources\":[{\"accountId\":\"1111111111\",\"type\":\"AWS::EFS::FileSystem\",\"ARN\":\"arn:aws:elasticfilesystem:eu-central-1:1111111111:file-system/fs-00000000\"},{\"accountId\":\"1111111111\",\"type\":\"AWS::EFS::AccessPoint\",\"ARN\":\"arn:aws:elasticfilesystem:eu-central-1:1111111111:access-point/fsap-00000000000000000\"}],\"eventType\":\"AwsServiceEvent\",\"managementEvent\":true,\"recipientAccountId\":\"1111111111\",\"serviceEventDetails\":{\"permissions\":{\"ClientRootAccess\":false,\"ClientMount\":true,\"ClientWrite\":true},\"sourceIpAddress\":\"1.2.3.4\"},\"eventCategory\":\"Management\"}\n",
        "event": {
            "kind": "event",
            "category": [
                "network"
            ],
            "type": [
                "access"
            ],
            "dataset": "cloudtrail",
            "action": "NewClientConnection",
            "provider": "elasticfilesystem.amazonaws.com"
        },
        "@timestamp": "2022-09-09T09:17:32.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "eu-central-1",
            "account": {
                "id": "1111111111"
            }
        },
        "action": {
            "type": "AwsServiceEvent",
            "name": "NewClientConnection",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "1111111111",
                "userIdentity": {
                    "type": "AssumedRole",
                    "principalId": "AR0000000000000000:1111111111111111111111111",
                    "arn": "arn:aws:sts::1111111111:assumed-role/role/1111111111111111111111111",
                    "accountId": "1111111111",
                    "accessKeyId": "AS000000000000000000",
                    "sessionContext": {
                        "sessionIssuer": {
                            "type": "Role",
                            "principalId": "AR0000000000000000",
                            "arn": "arn:aws:iam::1111111111:role/service-role/username",
                            "accountId": "1111111111",
                            "userName": "username"
                        },
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-09-09T07:45:14Z",
                            "mfaAuthenticated": "false"
                        }
                    }
                },
                "resources": [
                    {
                        "accountId": "1111111111",
                        "type": "AWS::EFS::FileSystem",
                        "ARN": "arn:aws:elasticfilesystem:eu-central-1:1111111111:file-system/fs-00000000"
                    },
                    {
                        "accountId": "1111111111",
                        "type": "AWS::EFS::AccessPoint",
                        "ARN": "arn:aws:elasticfilesystem:eu-central-1:1111111111:access-point/fsap-00000000000000000"
                    }
                ]
            }
        },
        "user_agent": {
            "original": "elasticfilesystem"
        },
        "user": {
            "id": "1111111111"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.08",
                "recipient_account_id": "1111111111",
                "user_identity": {
                    "type": "AssumedRole",
                    "principalId": "AR0000000000000000:1111111111111111111111111",
                    "arn": "arn:aws:sts::1111111111:assumed-role/role/1111111111111111111111111",
                    "accountId": "1111111111",
                    "accessKeyId": "AS000000000000000000",
                    "sessionContext": {
                        "sessionIssuer": {
                            "type": "Role",
                            "principalId": "AR0000000000000000",
                            "arn": "arn:aws:iam::1111111111:role/service-role/username",
                            "accountId": "1111111111",
                            "userName": "username"
                        },
                        "webIdFederationData": {},
                        "attributes": {
                            "creationDate": "2022-09-09T07:45:14Z",
                            "mfaAuthenticated": "false"
                        }
                    }
                },
                "resources": [
                    {
                        "accountId": "1111111111",
                        "type": "AWS::EFS::FileSystem",
                        "ARN": "arn:aws:elasticfilesystem:eu-central-1:1111111111:file-system/fs-00000000"
                    },
                    {
                        "accountId": "1111111111",
                        "type": "AWS::EFS::AccessPoint",
                        "ARN": "arn:aws:elasticfilesystem:eu-central-1:1111111111:access-point/fsap-00000000000000000"
                    }
                ]
            }
        }
    }
    	
	```


=== "test_signin2.json"

    ```json
	
    {
        "message": "{\"eventVersion\":\"1.08\",\"userIdentity\":{\"type\":\"AssumedRole\",\"principalId\":\"A00000000000000000000:user@example.org\",\"arn\":\"arn:aws:sts::111111111:assumed-role/role/user@example.org\",\"accountId\":\"111111111\"},\"eventTime\":\"2022-09-08T15:01:59Z\",\"eventSource\":\"signin.amazonaws.com\",\"eventName\":\"ConsoleLogin\",\"awsRegion\":\"us-east-1\",\"sourceIPAddress\":\"1.2.3.4\",\"userAgent\":\"Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36\",\"requestParameters\":null,\"responseElements\":{\"ConsoleLogin\":\"Success\"},\"additionalEventData\":{\"LoginTo\":\"https://console.aws.amazon.com/console/home\",\"MobileVersion\":\"No\",\"MFAUsed\":\"No\",\"SamlProviderArn\":\"arn:aws:iam::111111111:saml-provider/provider-name\"},\"eventID\":\"e7dd6d97-2d3a-45dc-bb19-a3ea347091e3\",\"readOnly\":false,\"eventType\":\"AwsConsoleSignIn\",\"managementEvent\":true,\"recipientAccountId\":\"111111111\",\"eventCategory\":\"Management\",\"tlsDetails\":{\"tlsVersion\":\"TLSv1.2\",\"cipherSuite\":\"ECDHE-RSA-AES128-GCM-SHA256\",\"clientProvidedHostHeader\":\"signin.aws.amazon.com\"}}\n",
        "event": {
            "kind": "event",
            "category": [
                "authentication"
            ],
            "type": [
                "allowed"
            ],
            "dataset": "cloudtrail",
            "action": "ConsoleLogin",
            "provider": "signin.amazonaws.com"
        },
        "@timestamp": "2022-09-08T15:01:59.000000Z",
        "cloud": {
            "provider": "aws",
            "service": {
                "name": "cloudtrail"
            },
            "region": "us-east-1",
            "account": {
                "id": "111111111"
            }
        },
        "action": {
            "type": "AwsConsoleSignIn",
            "name": "ConsoleLogin",
            "outcome": "success",
            "target": "network-traffic",
            "properties": {
                "recipientAccountId": "111111111",
                "userIdentity": {
                    "type": "AssumedRole",
                    "principalId": "A00000000000000000000:user@example.org",
                    "arn": "arn:aws:sts::111111111:assumed-role/role/user@example.org",
                    "accountId": "111111111"
                }
            }
        },
        "user_agent": {
            "original": "Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/105.0.0.0 Safari/537.36"
        },
        "user": {
            "id": "111111111"
        },
        "source": {
            "address": "1.2.3.4",
            "ip": "1.2.3.4"
        },
        "tls": {
            "cipher": "ECDHE-RSA-AES128-GCM-SHA256",
            "version": "TLSv1.2"
        },
        "aws": {
            "cloudtrail": {
                "event_version": "1.08",
                "recipient_account_id": "111111111",
                "user_identity": {
                    "type": "AssumedRole",
                    "principalId": "A00000000000000000000:user@example.org",
                    "arn": "arn:aws:sts::111111111:assumed-role/role/user@example.org",
                    "accountId": "111111111"
                },
                "flattened": {
                    "response_elements": "{\"ConsoleLogin\": \"Success\"}"
                }
            }
        },
        "related": {
            "ip": [
                "1.2.3.4"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`action.properties.errorCode` | `keyword` | The code of the error associated to the request |
|`action.properties.errorMessage` | `keyword` | The message of the error associated to the request |
|`action.properties.recipientAccountId` | `keyword` | The account ID that received the event |
|`action.properties.requestParameters.userData` | `keyword` | The userData parameters sent with the request |
|`action.properties.resources` | `list` | A list of resources accessed in the event |
|`action.properties.responseElements.pendingModifiedValues.masterUserPassword` | `keyword` | The new master password for the RDS instance |
|`action.properties.responseElements.publiclyAccessible` | `boolean` | Whether the requested ressource was public |
|`action.properties.userIdentity` | `object` | Information about the user that made the request |
|`action.target` | `keyword` | The target of the action |
|`aws.cloudtrail.event_version` | `keyword` | The version of the event |
|`aws.cloudtrail.flattened.request_parameters` | `keyword` | The flattened version of the field requestParameters |
|`aws.cloudtrail.flattened.response_elements` | `keyword` | The flattened version of the field responseElements |
|`aws.cloudtrail.insight_details.context` | `keyword` | The context of the insight |
|`aws.cloudtrail.insight_details.state` | `keyword` | The status of the insight |
|`aws.cloudtrail.insight_details.type` | `keyword` | The type of the insight |
|`aws.cloudtrail.recipient_account_id` | `keyword` | The account ID that received the event |
|`aws.cloudtrail.request_parameters.userData` | `keyword` | The userData parameters sent with the request |
|`aws.cloudtrail.request_parameters.userName` | `keyword` | The name of the user sent in the request |
|`aws.cloudtrail.resources` | `list` | A list of resources accessed in the event |
|`aws.cloudtrail.response_elements.pendingModifiedValues.masterUserPassword` | `keyword` | The new master password for the RDS instance |
|`aws.cloudtrail.response_elements.publiclyAccessible` | `boolean` | Whether the requested ressource was public |
|`aws.cloudtrail.response_elements.user.arn` | `keyword` | The arn of the user in the response |
|`aws.cloudtrail.response_elements.user.userName` | `keyword` | The name of the user in the response |
|`cloud.account.id` | `keyword` | The cloud account or organization id. |
|`cloud.instance.id` | `keyword` | Instance ID of the host machine. |
|`cloud.provider` | `keyword` | Name of the cloud provider. |
|`cloud.region` | `keyword` | Region in which this host, resource, or service is located. |
|`cloud.service.name` | `keyword` | The cloud service name. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.category` | `keyword` | Event category. The second categorization field in the hierarchy. |
|`event.code` | `keyword` | Identification code for this event. |
|`event.dataset` | `keyword` | Name of the dataset. |
|`event.kind` | `keyword` | The kind of the event. The highest categorization field in the hierarchy. |
|`event.provider` | `keyword` | Source of the event. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.type` | `keyword` | Event type. The third categorization field in the hierarchy. |
|`source.address` | `keyword` | Source network address. |
|`source.domain` | `keyword` | The domain name of the source. |
|`source.ip` | `ip` | IP address of the source. |
|`tls.cipher` | `keyword` | String indicating the cipher used during the current connection. |
|`tls.version` | `keyword` | Numeric part of the version parsed from the original string. |
|`user.id` | `keyword` | Unique identifier of the user. |
|`user.name` | `keyword` | Short name or login of the user. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

