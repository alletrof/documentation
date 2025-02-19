


## Event Samples

Find below few samples of events and how they are normalized by SEKOIA.IO.


=== "cisco_esa_cef.json"

    ```json
	
    {
        "message": "CEF:0|Cisco|C390 Email Security Appliance|14.0.0-698|ESA_CONSOLIDATED_LOG_EVENT|Consolidated Log Event|5|deviceExternalId=123456789-54646546546 ESAMID=12356 ESAICID=123456 ESADCID=123456 ESAAMPVerdict=NOT_EVALUATED ESAASVerdict=NOT_EVALUATED ESAAVVerdict=NOT_EVALUATED ESACFVerdict=MATCH endTime=Mon Aug  1 03:34:23 2022 dvc=1.1.1.1 ESAFriendlyFrom=noreply@corp.net ESAGMVerdict=NOT_EVALUATED startTime=Mon Aug  1 03:30:36 2022 deviceOutboundInterface=OutgoingMail deviceDirection=1 ESAMailFlowPolicy=RELAY suser=noreply@corp.net cs1Label=MailPolicy cs1=RestrictionEmetteur cs2Label=SenderCountry cs2=not enabled ESAMFVerdict=NO_MATCH act=DELIVERED cs4Label=ExternalMsgID cs4='<123456@corp.net>' ESAMsgSize=3059 ESAOFVerdict=NOT_EVALUATED duser=foo@other-corp.com ESAHeloDomain=foo.bar.net ESAHeloIP=2.2.2.2 cfp1Label=SBRSScore cfp1=not enabled sourceHostName=unknown ESASenderGroup=RELAYLIST sourceAddress=2.2.2.2 msg='\\=?ISO-8859-15?Q?foo\\=20bar\\=20baz\\=20-\\=123456789?\\='\n\n",
        "event": {
            "severity": 5,
            "action": "DELIVERED",
            "reason": "'\\=?ISO-8859-15?Q?foo\\=20bar\\=20baz\\=20-\\=123456789?\\='\n\n",
            "end": "2022-08-01T03:34:23.000000Z",
            "start": "2022-08-01T03:30:36.000000Z"
        },
        "@timestamp": "2022-08-01T03:30:36.000000Z",
        "observer": {
            "vendor": "Cisco",
            "type": "C390 Email Security Appliance",
            "version": "14.0.0-698"
        },
        "rule": {
            "id": "ESA_CONSOLIDATED_LOG_EVENT"
        },
        "source": {
            "ip": "2.2.2.2",
            "user": {
                "name": "noreply@corp.net"
            },
            "address": "2.2.2.2"
        },
        "network": {
            "direction": "outbound"
        },
        "destination": {
            "user": {
                "name": "foo@other-corp.com"
            }
        },
        "server": {
            "ip": "1.1.1.1"
        },
        "host": {
            "hostname": "unknown",
            "name": "unknown"
        },
        "cef": {
            "event_type": "base event"
        },
        "related": {
            "hosts": [
                "unknown"
            ],
            "user": [
                "foo@other-corp.com",
                "noreply@corp.net"
            ],
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "cisco_esa_cef_no_starttime.json"

    ```json
	
    {
        "message": "CEF:0|Cisco|C390 Email Security Appliance|14.0.0-698|ESA_CONSOLIDATED_LOG_EVENT|Consolidated Log Event|5|deviceExternalId=ABC123 ESAMID=123 E SAAMPVerdict=NOT_EVALUATED ESAASVerdict=NOT_EVALUATED ESAAVVerdict=NOT_EVALUATED ESACFVerdict=MATCH endTime=Mon Aug  1 06:40:30 2022 ESAGMVerdict=NOT_EVALUATED ESAMFVerdict=NO_MATCH ESAOFVerdict=NOT_EVALUATED ESAStatus=QUEUED\n\n",
        "event": {
            "severity": 5,
            "end": "2022-08-01T06:40:30.000000Z"
        },
        "observer": {
            "vendor": "Cisco",
            "type": "C390 Email Security Appliance",
            "version": "14.0.0-698"
        },
        "rule": {
            "id": "ESA_CONSOLIDATED_LOG_EVENT"
        },
        "@timestamp": "2022-08-01T06:40:30.000000Z",
        "cef": {
            "Name": "Consolidated Log Event"
        }
    }
    	
	```


=== "cyber_reason_malop_connection.json"

    ```json
	
    {
        "message": "CEF:0|Cybereason|Cybereason|1.0|5|Malop Connection Added|5|CybereasonCEFgeneratorBatchId1=58bc2665-b22f-4345-bd90-3f84be47c8b6 cs1=11.1323449861766643222 CybereasonCEFgeneratorcountry1Name=None dst=3.226.77.3 dpt=443 rt=1629500007043 cs1Label=MalopId",
        "event": {
            "severity": 5
        },
        "observer": {
            "vendor": "Cybereason",
            "type": "Cybereason",
            "version": "1.0"
        },
        "rule": {
            "id": "5"
        },
        "destination": {
            "port": 443,
            "ip": "3.226.77.3",
            "address": "3.226.77.3"
        },
        "@timestamp": "2021-08-20T22:53:27.043000Z",
        "cef": {
            "cs1Label": "MalopId",
            "rt": "1629500007043",
            "dpt": "443",
            "cs1": "11.1323449861766643222",
            "Name": "Malop Connection Added"
        },
        "related": {
            "ip": [
                "3.226.77.3"
            ]
        }
    }
    	
	```


=== "cyber_reason_malop_created.json"

    ```json
	
    {
        "message": "CEF:0|Cybereason|Cybereason|1.0|1|Malop Created|5|rt=1629701622409 deviceCustomDate1=1636629776184 deviceFacility=Under Investigation CybereasonCEFgeneratorBatchId1=078e369b-ea4e-4e98-bc0d-ee71fd40d19d cs1=11.4718101284717793977 cs2=EXTENSION_MANIPULATION cs3=MALICIOUS_INFECTION cs5=maliciousByDualExtensionByFileRootCause cn1=1 cs6=https://yourserver.cybereason.net:8443//#/malop/11.4718101284717793977 cn2=1 cs4=bb9dbdca921d84381c893086f65ffca17120b23d requestContext=flashget3.7.0.1220en.pdf.exe, which has an unknown reputation, has dual extensions, which is hiding the true nature of the process. cs1Label=MalopId cs2Label=MalopDetectionType cs3Label=MalopActivityType cs4Label=MalopHashList cs5Label=DecisionFeatures cs6Label=IncidentLink cn1Label=AffectedMachinesCount cn2Label=AffectedUsersCount cn3Label=isSigned deviceCustomDate1Label=ModifiedTime",
        "event": {
            "severity": 5
        },
        "observer": {
            "vendor": "Cybereason",
            "type": "Cybereason",
            "version": "1.0"
        },
        "rule": {
            "id": "1"
        },
        "log": {
            "syslog": {
                "facility": {
                    "name": "Under Investigation"
                }
            }
        },
        "http": {
            "request": {
                "referrer": "flashget3.7.0.1220en.pdf.exe, which has an unknown reputation, has dual extensions, which is hiding the true nature of the process."
            }
        },
        "@timestamp": "2021-08-23T06:53:42.409000Z",
        "cef": {
            "cn2Label": "AffectedUsersCount",
            "cn1Label": "AffectedMachinesCount",
            "cs6Label": "IncidentLink",
            "cs5Label": "DecisionFeatures",
            "cs4Label": "MalopHashList",
            "cs3Label": "MalopActivityType",
            "cs2Label": "MalopDetectionType",
            "cs1Label": "MalopId",
            "cs4": "bb9dbdca921d84381c893086f65ffca17120b23d",
            "cn2": 1,
            "cs6": "https://yourserver.cybereason.net:8443//#/malop/11.4718101284717793977",
            "cn1": 1,
            "cs5": "maliciousByDualExtensionByFileRootCause",
            "cs3": "MALICIOUS_INFECTION",
            "cs2": "EXTENSION_MANIPULATION",
            "cs1": "11.4718101284717793977",
            "rt": "1629701622409",
            "Name": "Malop Created"
        }
    }
    	
	```


=== "cyber_reason_malop_machine.json"

    ```json
	
    {
        "message": "CEF:0|Cybereason|Cybereason|1.0|3|Malop Machine Added|5|destinationDnsDomain=desktop-aas6kq7 dst=10.0.2.15 destinationTranslatedAddress=117.99.232.147 CybereasonCEFgeneratorBatchId1=2ac124fd-def2-4073-b408-d3b3f0e764b0 cs1=11.-6654920844431693523 flexString2=True dhost=desktop-aas6kq7 CybereasonCEFgeneratorOSandVersion1=Windows_10 CybereasonCEFgeneratorMachineGuid1=-592942600.1198775089551518743 cfp3=1 rt=1625748509151 cfp2=1 cs1Label=MalopId flexString2Label=isMalicious cfp2Label=isOnline cfp3Label=isOriginalMachine request=\"C:\\\\Users\\\\chand\\\\Downloads\\\\BT_21.40.5_32_Win7.pdf.exe\" deviceProcessName=explorer.exe CybereasonCEFgeneratorChildProcess1=None",
        "event": {
            "severity": 5
        },
        "observer": {
            "vendor": "Cybereason",
            "type": "Cybereason",
            "version": "1.0"
        },
        "rule": {
            "id": "3"
        },
        "destination": {
            "domain": "desktop-aas6kq7",
            "ip": "10.0.2.15",
            "address": "desktop-aas6kq7"
        },
        "url": {
            "original": "C:\\\\Users\\\\chand\\\\Downloads\\\\BT_21.40.5_32_Win7.pdf.exe",
            "path": "\\\\Users\\\\chand\\\\Downloads\\\\BT_21.40.5_32_Win7.pdf.exe",
            "scheme": "c"
        },
        "@timestamp": "2021-07-08T12:48:29.151000Z",
        "cef": {
            "cfp3Label": "isOriginalMachine",
            "cfp2Label": "isOnline",
            "flexString2Label": "isMalicious",
            "cs1Label": "MalopId",
            "cfp2": 1,
            "rt": "1625748509151",
            "cfp3": 1,
            "flexString2": "True",
            "cs1": "11.-6654920844431693523",
            "Name": "Malop Machine Added"
        },
        "related": {
            "hosts": [
                "desktop-aas6kq7"
            ],
            "ip": [
                "10.0.2.15"
            ]
        }
    }
    	
	```


=== "cyber_reason_malop_process_added.json"

    ```json
	
    {
        "message": "CEF:0|Cybereason|Cybereason|1.0|2|Malop Process Added|5|CybereasonCEFgeneratorBatchId1=2ac124fd-def2-4073-b408-d3b3f0e764b0 cs1=11.-6654920844431693523 cs4=76030baf8e80653b883474f56c06164c33417ece request=\"C:\\\\Users\\\\chand\\\\Downloads\\\\BT_21.40.5_32_Win7.pdf.exe\" flexString2=True cn3=1 reason=indifferent rt=1629700682928 cs1Label=MalopId flexString2Label=isMalicious cs4Label=processSha1 cn3Label=isSigned",
        "event": {
            "severity": 5,
            "action": "indifferent"
        },
        "observer": {
            "vendor": "Cybereason",
            "type": "Cybereason",
            "version": "1.0"
        },
        "rule": {
            "id": "2"
        },
        "url": {
            "original": "C:\\\\Users\\\\chand\\\\Downloads\\\\BT_21.40.5_32_Win7.pdf.exe",
            "path": "\\\\Users\\\\chand\\\\Downloads\\\\BT_21.40.5_32_Win7.pdf.exe",
            "scheme": "c"
        },
        "@timestamp": "2021-08-23T06:38:02.928000Z",
        "cef": {
            "cs4Label": "processSha1",
            "flexString2Label": "isMalicious",
            "cs1Label": "MalopId",
            "rt": "1629700682928",
            "cn3": 1,
            "flexString2": "True",
            "cs4": "76030baf8e80653b883474f56c06164c33417ece",
            "cs1": "11.-6654920844431693523",
            "Name": "Malop Process Added"
        }
    }
    	
	```


=== "cyber_reason_malop_user.json"

    ```json
	
    {
        "message": "CEF:0|Cybereason|Cybereason|1.0|6|Malop User Added|5|CybereasonCEFgeneratorBatchId1=2ac124fd-def2-4073-b408-d3b3f0e764b0 cs1=11.-6654920844431693523 dpriv=None dhost=desktop-aas6kq7 CybereasonCEFgeneratorOrganizationName1=INTEGRATION duser=system cs1Label=MalopId",
        "event": {
            "severity": 5
        },
        "observer": {
            "vendor": "Cybereason",
            "type": "Cybereason",
            "version": "1.0"
        },
        "rule": {
            "id": "6"
        },
        "destination": {
            "domain": "desktop-aas6kq7",
            "user": {
                "name": "system"
            },
            "address": "desktop-aas6kq7"
        },
        "cef": {
            "cs1Label": "MalopId",
            "dpriv": "None",
            "cs1": "11.-6654920844431693523",
            "Name": "Malop User Added"
        },
        "related": {
            "user": [
                "system"
            ],
            "hosts": [
                "desktop-aas6kq7"
            ]
        }
    }
    	
	```


=== "fortigate_Configuration_changed.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.2.9|32102|event:system|7|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0100032102 cat=event:system FortinetFortiGatesubtype=system FortinetFortiGatelevel=alert FortinetFortiGatevd=root FortinetFortiGateeventtime=1637681708541881380 FortinetFortiGatetz=+0100 FortinetFortiGatelogdesc=Configuration changed duser= sproc=console msg=Configuration is changed in the admin session",
        "event": {
            "severity": 7,
            "reason": "Configuration is changed in the admin session"
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v6.2.9"
        },
        "rule": {
            "id": "32102"
        },
        "cef": {
            "sproc": "console",
            "cat": "event:system",
            "Name": "event:system"
        }
    }
    	
	```


=== "fortigate_anomaly.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v5.6.0|18433|anomaly:anomaly clear_ session|7|FTNTFGTlogid=0720018433 cat=anomaly:anomaly FTNTFGTsubtype=anomaly FTNTFGTlevel=alert FTNTFGTvd=vdom1 FTNTFGTseverity=critical src=1.1.1.1 dst=2.2.2.2 deviceInboundInterface=port15 externalId=0 act=clear_session proto=1 app=icmp/146/81 cnt=306 FTNTFGTattack=icmp_flood dpt=20882 FTNTFGTicmptype=0x92 FTNTFGTicmpcode=0x51 FTNTFGTattackid=16777316 FTNTFGTprofile=DoS-policy1 cs2=http://www.fortinet.com/ids/VID16777316 cs2Label=Reference msg=anomaly: icmp_flood, 34 > threshold 25, repeats 306 times FTNTFGTcrscore=50 FTNTFGTcrlevel=critical",
        "event": {
            "severity": 7,
            "action": "clear_session",
            "reason": "anomaly: icmp_flood, 34 > threshold 25, repeats 306 times"
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v5.6.0"
        },
        "rule": {
            "id": "18433"
        },
        "network": {
            "protocol": "icmp/146/81",
            "transport": "icmp"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "destination": {
            "port": 20882,
            "ip": "2.2.2.2",
            "address": "2.2.2.2"
        },
        "cef": {
            "cs2Label": "Reference",
            "cs2": "http://www.fortinet.com/ids/VID16777316",
            "dpt": "20882",
            "cnt": 306,
            "externalId": "0",
            "cat": "anomaly:anomaly",
            "Name": "anomaly:anomaly clear_ session"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "fortigate_antivirus.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v5.6.0|08192|utm:virus infected blocked|4|FTNTFGTlogid=0211008192 cat=utm:virus FTNTFGTsubtype=virus FTNTFGTeventtype=infected FTNTFGTlevel=warning FTNTFGTvd=vdom1 msg=File is infected act=blocked app=HTTP externalId=56633 src=1.1.1.1 dst=2.2.2.2 spt=45719 dpt=80 deviceInboundInterface=port15 deviceOutboundInterface=port19 proto=6 deviceDirection=0 fname=eicar.com FTNTFGTchecksum=1dd02bdb FTNTFGTquarskip=No-skip cs1=EICAR_TEST_FILE cs1Label=Virus FTNTFGTdtype=Virus cs2=http://www.fortinet.com/ve?vn\\=EICAR_TEST_FILE cs2Label=Reference FTNTFGTvirusid=2172 request=http://2.2.2.2/eicar.com FTNTFGTprofile=default duser= requestClientApplication=Wget/1 10 2 FTNTFGTanalyticscksum=131f95c51cc819465fa1797f6ccacf9d494aaaff46fa3eac73ae63ffbdfd8267 FTNTFGTanalyticssubmit=false FTNTFGTcrscore=50 FTNTFGTcrlevel=critical",
        "event": {
            "severity": 4,
            "action": "blocked",
            "reason": "File is infected"
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v5.6.0"
        },
        "rule": {
            "id": "08192"
        },
        "network": {
            "protocol": "HTTP",
            "direction": "inbound",
            "transport": "tcp"
        },
        "file": {
            "name": "eicar.com"
        },
        "source": {
            "ip": "1.1.1.1",
            "port": 45719,
            "address": "1.1.1.1"
        },
        "destination": {
            "port": 80,
            "ip": "2.2.2.2",
            "address": "2.2.2.2"
        },
        "url": {
            "original": "http://2.2.2.2/eicar.com",
            "domain": "2.2.2.2",
            "path": "/eicar.com",
            "scheme": "http",
            "port": 80
        },
        "cef": {
            "cs2Label": "Reference",
            "cs2": "http://www.fortinet.com/ve?vn\\=EICAR_TEST_FILE",
            "cs1Label": "Virus",
            "cs1": "EICAR_TEST_FILE",
            "dpt": "80",
            "externalId": "56633",
            "cat": "utm:virus",
            "Name": "utm:virus infected blocked"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "fortigate_icmp_CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.10|00014|traffic:local accept|3|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0001000014 cat=traffic:local FortinetFortiGatesubtype=local FortinetFortiGatelevel=notice FortinetFortiGatevd=root FortinetFortiGateeventtime=1602663098 src=1.1.1.1 deviceInboundInterface=port1 FortinetFortiGatesrcintfrole=undefined dst=2.2.2.2 deviceOutboundInterface=root FortinetFortiGatedstintfrole=undefined externalId=4887198 proto=1 FortinetFortiGateaction=accept FortinetFortiGatepolicyid=0 FortinetFortiGatepolicytype=local-in-policy app=icmp/8/0 FortinetFortiGatedstcountry=Reserved FortinetFortiGatesrccountry=China FortinetFortiGatetrandisp=noop FortinetFortiGateapp=icmp/8/0 FortinetFortiGateduration=61 out=84 in=84 FortinetFortiGatesentpkt=1 FortinetFortiGatercvdpkt=1 FortinetFortiGateappcat=unscanned",
        "event": {
            "severity": 3
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v6.0.10"
        },
        "rule": {
            "id": "00014"
        },
        "network": {
            "protocol": "icmp/8/0",
            "transport": "icmp"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "destination": {
            "ip": "2.2.2.2",
            "address": "2.2.2.2"
        },
        "host": {
            "network": {
                "ingress": {
                    "bytes": 84
                },
                "egress": {
                    "bytes": 84
                }
            }
        },
        "cef": {
            "externalId": "4887198",
            "cat": "traffic:local",
            "Name": "traffic:local accept"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "fortigate_ssh_access.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.4|32021|event:system login failed|7|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0100032021 cat=event:system FortinetFortiGatesubtype=system FortinetFortiGatelevel=alert FortinetFortiGatevd=root FortinetFortiGateeventtime=1579172447 FortinetFortiGatelogdesc=Admin login disabled sproc=1.1.1.1 FortinetFortiGateaction=login outcome=failed reason=exceed_limit msg=Login disabled from IP 1.1.1.1 for 60 seconds because of 3 bad attempts",
        "event": {
            "severity": 7,
            "reason": "Login disabled from IP 1.1.1.1 for 60 seconds because of 3 bad attempts",
            "action": "exceed_limit"
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v6.0.4"
        },
        "rule": {
            "id": "32021"
        },
        "cef": {
            "sproc": "1.1.1.1",
            "cat": "event:system",
            "Name": "event:system login failed"
        }
    }
    	
	```


=== "fortigate_ssl_new_con.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.10|39943|event:vpn ssl-new-con|2|deviceExternalId=FGT3HD3916803645 FTNTFGTlogid=0101039943 cat=event:vpn FTNTFGTsubtype=vpn FTNTFGTlevel=information FTNTFGTvd=root FTNTFGTeventtime=1637338258 FTNTFGTlogdesc=SSL VPN new connection act=ssl-new-con FTNTFGTtunneltype=ssl FTNTFGTtunnelid=0 dst=2.2.2.2 duser=N/A FTNTFGTgroup=N/A FTNTFGTdst_host=N/A reason=N/A msg=SSL new connection",
        "event": {
            "severity": 2,
            "action": "N/A",
            "reason": "SSL new connection"
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v6.0.10"
        },
        "rule": {
            "id": "39943"
        },
        "destination": {
            "ip": "2.2.2.2",
            "user": {
                "name": "N/A"
            },
            "address": "2.2.2.2"
        },
        "cef": {
            "cat": "event:vpn",
            "Name": "event:vpn ssl-new-con"
        },
        "related": {
            "user": [
                "N/A"
            ],
            "ip": [
                "2.2.2.2"
            ]
        }
    }
    	
	```


=== "fortigate_traffic_forward.CEF.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v5.6.0|00013|traffic:forward close|3|FTNTFGTlogid=0000000013 cat=traffic:forward FTNTFGTsubtype=forward FTNTFGTlevel=notice FTNTFGTvd=vdom1 src=2.2.2.2 shost=2.2.2.2 spt=45719 deviceInboundInterface=port15 dst=3.3.3.3 dhost=3.3.3.3 dpt=80 deviceOutboundInterface=port19 FTNTFGTpoluuid=61c4243a-34ba-51e5-c32a-3859389a5162 externalId=56633 proto=6 act=close cs5=10 cs5Label=Policy Id FTNTFGTdstcountry=Reserved FTNTFGTsrccountry=Reserved FTNTFGTtrandisp=snat sourceTranslatedAddress=1.1.1.1 sourceTranslatedPort=45719 app=HTTP FTNTFGTappid=38783 FTNTFGTapp=Wget.Like FTNTFGTappcat=General.Interest FTNTFGTapprisk=low FTNTFGTapplist=default FTNTFGTappact=detected cn1=7 cn1Label=Duration out=398 in=1605 cn2=5 cn2Label=Packets Sent cn3=5 cn3Label=Packets Received FTNTFGTutmaction=block FTNTFGTcountav=1 FTNTFGTcountapp=1 FTNTFGTcrscore=50 FTNTFGTcraction=2",
        "event": {
            "severity": 3,
            "action": "close"
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v5.6.0"
        },
        "rule": {
            "id": "00013"
        },
        "network": {
            "protocol": "HTTP",
            "transport": "tcp"
        },
        "source": {
            "ip": "2.2.2.2",
            "port": 45719,
            "address": "2.2.2.2"
        },
        "destination": {
            "domain": "3.3.3.3",
            "port": 80,
            "ip": "3.3.3.3",
            "address": "3.3.3.3"
        },
        "host": {
            "network": {
                "ingress": {
                    "bytes": 1605
                },
                "egress": {
                    "bytes": 398
                }
            },
            "hostname": "2.2.2.2",
            "name": "2.2.2.2"
        },
        "cef": {
            "cn3": 5,
            "cn2Label": "Packets Sent",
            "cn2": 5,
            "cn1Label": "Duration",
            "cn1": 7,
            "cs5Label": "Policy Id",
            "cs5": "10",
            "externalId": "56633",
            "dpt": "80",
            "cat": "traffic:forward",
            "Name": "traffic:forward close"
        },
        "related": {
            "hosts": [
                "2.2.2.2",
                "3.3.3.3"
            ],
            "ip": [
                "2.2.2.2",
                "3.3.3.3"
            ]
        }
    }
    	
	```


=== "fortigate_traffic_forward.CEF_2.json"

    ```json
	
    {
        "message": "CEF:0|Fortinet|Fortigate|v6.0.4|00013|traffic:forward timeout|3|deviceExternalId=FGVM2V0000171868 FortinetFortiGatelogid=0000000013 cat=traffic:forward FortinetFortiGatesubtype=forward FortinetFortiGatelevel=notice FortinetFortiGatevd=root FortinetFortiGateeventtime=1572471876 src=1.1.1.1 spt=49260 deviceInboundInterface=port1 FortinetFortiGatesrcintfrole=undefined dst=3.3.3.3 dpt=80 deviceOutboundInterface=port2 FortinetFortiGatedstintfrole=undefined FortinetFortiGatepoluuid=bafe134e-c0ad-51e8-ed9c-52f798dd69d4 externalId=12812952 proto=6 FortinetFortiGateaction=timeout FortinetFortiGatepolicyid=1 FortinetFortiGatepolicytype=policy app=HTTP FortinetFortiGatedstcountry=Reserved FortinetFortiGatesrccountry=United States FortinetFortiGatetrandisp=dnat destinationTranslatedAddress=2.2.2.2 destinationTranslatedPort=80 FortinetFortiGateduration=20 out=48 in=144 FortinetFortiGatesentpkt=1 FortinetFortiGatercvdpkt=3 FortinetFortiGateappcat=unscanned FortinetFortiGatecrscore=5 FortinetFortiGatecraction=262144 FortinetFortiGatecrlevel=low",
        "event": {
            "severity": 3
        },
        "observer": {
            "vendor": "Fortinet",
            "type": "Fortigate",
            "version": "v6.0.4"
        },
        "rule": {
            "id": "00013"
        },
        "network": {
            "protocol": "HTTP",
            "transport": "tcp"
        },
        "source": {
            "ip": "1.1.1.1",
            "port": 49260,
            "address": "1.1.1.1"
        },
        "destination": {
            "port": 80,
            "ip": "3.3.3.3",
            "address": "3.3.3.3"
        },
        "host": {
            "network": {
                "ingress": {
                    "bytes": 144
                },
                "egress": {
                    "bytes": 48
                }
            }
        },
        "cef": {
            "externalId": "12812952",
            "dpt": "80",
            "cat": "traffic:forward",
            "Name": "traffic:forward timeout"
        },
        "related": {
            "ip": [
                "1.1.1.1",
                "3.3.3.3"
            ]
        }
    }
    	
	```


=== "imported_from_logstash.json"

    ```json
	
    {
        "message": "CEF:0|SEKOIA.IO|SIC|v0.3.12|666|Download|1|msg= sys.log downloaded by john.doe@example.com src=127.0.0.1 cn1=53 cn1Label=seconds cs1Label=type cs1=ssl_download cs2Label=location cs2=home fname=sys.log fsize=666 suser=john.doe@example.com",
        "event": {
            "severity": 1,
            "reason": " sys.log downloaded by john.doe@example.com"
        },
        "observer": {
            "vendor": "SEKOIA.IO",
            "type": "SIC",
            "version": "v0.3.12"
        },
        "rule": {
            "id": "666"
        },
        "file": {
            "name": "sys.log",
            "size": 666
        },
        "source": {
            "ip": "127.0.0.1",
            "user": {
                "name": "john.doe@example.com"
            },
            "address": "127.0.0.1"
        },
        "cef": {
            "cs2": "home",
            "cs2Label": "location",
            "cs1": "ssl_download",
            "cs1Label": "type",
            "cn1Label": "seconds",
            "cn1": 53,
            "Name": "Download"
        },
        "related": {
            "user": [
                "john.doe@example.com"
            ],
            "ip": [
                "127.0.0.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_auth_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|AUTH|Radius|3|ProfileToken=xxxxx dtz=UTC rt=Feb 28 2021 18:20:54 deviceExternalId=xxxxxxxxxxxxx PanOSConfigVersion=10.0 PanOSAuthenticatedUserDomain=paloaltonetwork PanOSAuthenticatedUserName=xxxxx PanOSAuthenticatedUserUUID= PanOSClientTypeName= PanOSCortexDataLakeTenantID=xxxxxxxxxxxxx PanOSIsDuplicateLog=false PanOSIsPrismaNetworks=false PanOSIsPrismaUsers=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSRuleMatched= start=Feb 28 2021 18:20:40 cs3=vsys1 cs3Label=VirtualLocation c6a2=::ffff:0 c6a2Label=Source IPv6 Address c6a3=::ffff:0 c6a3Label=Destination IPv6 Address duser=paloaltonetwork\\\\xxxxx cs2=paloaltonetwork\\\\xxxxx cs2Label=NormalizeUser fname=Authentication object2 cs4=DC cs4Label=AuthenticationPolicy cnt=33554432 cn2=-5257671089978343424 cn2Label=MFAAuthenticationID PanOSMFAVendor=Symantec VIP cs6=rs-logging cs6Label=LogSetting cs1=deny-attackers cs1Label=AuthServerProfile PanOSAuthenticationDescription=www.something cs5=Unknown cs5Label=ClientType msg=Invalid Certificate cn1=0 cn1Label=AuthFactorNo externalId=xxxxxxxxxxxxx PanOSDGHierarchyLevel1=11 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=xxxxx PanOSVirtualSystemID=1 PanOSAuthenticationProtocol=EAP-TTLS with PAP PanOSRuleMatchedUUID= PanOSTimeGeneratedHighResolution=Feb 28 2021 18:20:41 PanOSSourceDeviceCategory=src_category_list-1 PanOSSourceDeviceProfile=src_profile_list-1 PanOSSourceDeviceModel=src_model_list-1 PanOSSourceDeviceVendor=src_vendor_list-1 PanOSSourceDeviceOSFamily=src_osfamily_list-0 PanOSSourceDeviceOSVersion=src_osversion_list-2 PanOSSourceDeviceHost=src_host_list-0 PanOSSourceDeviceMac=src_mac_list-2 PanOSAuthCacheServiceRegion= PanOSUserAgentString= PanOSSessionID=",
        "event": {
            "severity": 3,
            "reason": "Invalid Certificate",
            "timezone": "UTC",
            "start": "2021-02-28T18:20:40.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "AUTH"
        },
        "file": {
            "name": "Authentication object2"
        },
        "destination": {
            "user": {
                "name": "paloaltonetwork\\\\xxxxx"
            }
        },
        "@timestamp": "2021-02-28T18:20:40.000000Z",
        "cef": {
            "externalId": "xxxxxxxxxxxxx",
            "cn1Label": "AuthFactorNo",
            "cn1": 0,
            "cs5Label": "ClientType",
            "cs5": "Unknown",
            "cs1Label": "AuthServerProfile",
            "cs1": "deny-attackers",
            "cs6Label": "LogSetting",
            "cs6": "rs-logging",
            "cn2Label": "MFAAuthenticationID",
            "cn2": -5257671089978343424,
            "cnt": 33554432,
            "cs4Label": "AuthenticationPolicy",
            "cs4": "DC",
            "cs2Label": "NormalizeUser",
            "cs2": "paloaltonetwork\\\\xxxxx",
            "c6a3Label": "Destination IPv6 Address",
            "c6a3": "::ffff:0",
            "c6a2Label": "Source IPv6 Address",
            "c6a2": "::ffff:0",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "rt": "Feb 28 2021 18:20:54",
            "Name": "Radius"
        },
        "related": {
            "user": [
                "paloaltonetwork\\\\xxxxx"
            ]
        }
    }
    	
	```


=== "pan_ngfw_decryption_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|DECRYPTION|end|3|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 20:35:54 PanOSDeviceSN=xxxxxxxxxxxxx PanOSConfigVersion=null start=Mar 01 2021 20:35:54 src=1.1.1.1 dst=1.1.1.1 sourceTranslatedAddress=1.1.1.1 destinationTranslatedAddress=1.1.1.1 cs1=allow-all-employees cs1Label=Rule suser=paloaltonetwork\\\\\\\\xxxxx duser=paloaltonetwork\\\\\\\\xxxxx app=gmail-base cs3=vsys1 cs3Label=VirtualLocation cs4=datacenter cs4Label=FromZone cs5=ethernet4Zone-test1 cs5Label=ToZone deviceInboundInterface=ethernet1/1 deviceOutboundInterface=tunnel.901 cs6=test cs6Label=LogSetting PanOSTimeReceivedManagementPlane=Dec 12 2019 22:16:48 cn1=106112 cn1Label=SessionID cnt=1 spt=16524 dpt=20122 sourceTranslatedPort=15856 destinationTranslatedPort=10128 proto=tcp act=deny PanOSTunnel=N/A PanOSSourceUUID= PanOSDestinationUUID= PanOSRuleUUID=fnullacnullnulle1-2c69-4f2b-8293-46ee4c73737e PanOSClientToFirewall=null PanOSFirewallToClient=null PanOSTLSVersion=null PanOSTLSKeyExchange=null PanOSTLSEncryptionAlgorithm=null PanOSTLSAuth=null PanOSPolicyName= PanOSEllipticCurve= PanOSErrorIndex=null PanOSRootStatus=null PanOSChainStatus=null PanOSProxyType=null PanOSCertificateSerial= PanOSFingerprint= PanOSTimeNotBefore=0 PanOSTimeNotAfter=0 PanOSCertificateVersion=null PanOSCertificateSize=0 PanOSCommonNameLength=0 PanOSIssuerNameLength=0 PanOSRootCNLength=0 PanOSSNILength=0 PanOSCertificateFlags=0 PanOSCommonName= PanOSIssuerCommonName= PanOSRootCommonName= PanOSServerNameIndication= PanOSErrorMessage= PanOSContainerID= PanOSContainerNameSpace= PanOSContainerName= PanOSSourceEDL= PanOSDestinationEDL= PanOSSourceDynamicAddressGroup= PanOSDestinationDynamicAddressGroup=test PanOSTimeGeneratedHighResolution=Jul 25 2019 23:30:12 PanOSSourceDeviceCategory= PanOSSourceDeviceProfile= PanOSSourceDeviceModel= PanOSSourceDeviceVendor= PanOSSourceDeviceOSFamily= PanOSSourceDeviceOSVersion= PanOSSourceDeviceHost= PanOSSourceDeviceMac= PanOSDestinationDeviceCategory= PanOSDestinationDeviceProfile= PanOSDestinationDeviceModel= PanOSDestinationDeviceVendor= PanOSDestinationDeviceOSFamily= PanOSDestinationDeviceOSVersion= PanOSDestinationDeviceHost= PanOSDestinationDeviceMac= externalId=xxxxxxxxxxxxx",
        "event": {
            "severity": 3,
            "action": "deny",
            "timezone": "UTC",
            "start": "2021-03-01T20:35:54.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "DECRYPTION"
        },
        "network": {
            "protocol": "gmail-base"
        },
        "source": {
            "ip": "1.1.1.1",
            "user": {
                "name": "paloaltonetwork\\\\\\\\xxxxx"
            },
            "port": 16524,
            "address": "1.1.1.1"
        },
        "destination": {
            "port": 20122,
            "ip": "1.1.1.1",
            "user": {
                "name": "paloaltonetwork\\\\\\\\xxxxx"
            },
            "address": "1.1.1.1"
        },
        "@timestamp": "2021-03-01T20:35:54.000000Z",
        "cef": {
            "externalId": "xxxxxxxxxxxxx",
            "dpt": "20122",
            "cnt": 1,
            "cn1Label": "SessionID",
            "cn1": 106112,
            "cs6Label": "LogSetting",
            "cs6": "test",
            "cs5Label": "ToZone",
            "cs5": "ethernet4Zone-test1",
            "cs4Label": "FromZone",
            "cs4": "datacenter",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "cs1Label": "Rule",
            "cs1": "allow-all-employees",
            "rt": "Mar 01 2021 20:35:54",
            "Name": "end"
        },
        "related": {
            "user": [
                "paloaltonetwork\\\\\\\\xxxxx"
            ],
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_file_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|THREAT|file|3|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 21:06:06 deviceExternalId=xxxxxxxxxxxxx PanOSConfigVersion= PanOSApplicationCategory=collaboration PanOSApplicationContainer= PanOSApplicationRisk=5 PanOSApplicationSubcategory=email PanOSApplicationTechnology=client-server PanOSCaptivePortal=false PanOSCloudHostname=PA-5220 PanOSCortexDataLakeTenantID=xxxxxxxxxxxxx PanOSDLPVersionFlag= PanOSDestinationDeviceClass= PanOSDestinationDeviceOS= dntdom= duser= duid= PanOSFileType=PNG File Upload PanOSInboundInterfaceDetailsPort=19 PanOSInboundInterfaceDetailsSlot=1 PanOSInboundInterfaceDetailsType=ethernet PanOSInboundInterfaceDetailsUnit=0 PanOSIsClienttoServer=false PanOSIsContainer=false PanOSIsDecryptMirror=false PanOSIsDecrypted= PanOSIsDuplicateLog=false PanOSIsEncrypted= PanOSIsIPV6= PanOSIsMptcpOn=false PanOSIsNonStandardDestinationPort=false PanOSIsPacketCapture=false PanOSIsPhishing=false PanOSIsPrismaNetwork=false PanOSIsPrismaUsers=false PanOSIsProxy=false PanOSIsReconExcluded=false PanOSIsSaaSApplication=false PanOSIsServertoClient=false PanOSIsSourceXForwarded= PanOSIsSystemReturn=false PanOSIsTransaction=false PanOSIsTunnelInspected=false PanOSIsURLDenied=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSNAT=false PanOSNonStandardDestinationPort=0 PanOSOutboundInterfaceDetailsPort=19 PanOSOutboundInterfaceDetailsSlot=1 PanOSOutboundInterfaceDetailsType=ethernet PanOSOutboundInterfaceDetailsUnit=0 PanOSPacket= PanOSProfileName= PanOSSanctionedStateOfApp=false PanOSSeverity=Low PanOSSourceDeviceClass= PanOSSourceDeviceOS= sntdom= suser= suid= PanOSThreatCategory= PanOSThreatNameFirewall= PanOSTunneledApplication=untunneled PanOSURL= PanOSUsers=1.1.1.1 PanOSVirtualSystemID=1 start=Mar 01 2021 21:06:06 src=1.1.1.1 dst=1.1.1.1 sourceTranslatedAddress=1.1.1.1 destinationTranslatedAddress=1.1.1.1 cs1=dg-log-policy cs1Label=Rule suser0= duser0= app=smtp cs3=smtp cs3Label=VirtualLocation cs4=tap cs4Label=FromZone cs5=tap cs5Label=ToZone deviceInboundInterface=ethernet1/19 deviceOutboundInterface=ethernet1/19 cs6=test cs6Label=LogSetting cn1=4016143 cn1Label=SessionID cnt=9 spt=37404 dpt=25 sourceTranslatedPort=0 destinationTranslatedPort=0 proto=tcp act=alert filePath=page-icon.png cs2=any cs2Label=URLCategory flexString2=client to server flexString2Label=DirectionOfAttack externalId=xxxxxxxxxxxxx PanOSSourceLocation=1.1.1.1-1.1.1.1 PanOSDestinationLocation=1.1.1.1-1.1.1.1 fileId=0 PanOSFileHash= PanOSReportID= PanOSDGHierarchyLevel1=12 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=PA-5220 PanOSSourceUUID= PanOSDestinationUUID= PanOSIMSI=0 PanOSIMEI= PanOSParentSessionID=0 PanOSParentStartTime=Jan 01 1970 00:00:00 PanOSTunnel=N/A PanOSContentVersion= PanOSSigFlags=0 PanOSRuleUUID= PanOSHTTP2Connection= PanOSDynamicUserGroup= PanOSX-Forwarded-ForIP= PanOSSourceDeviceCategory= PanOSSourceDeviceProfile= PanOSSourceDeviceModel= PanOSSourceDeviceVendor= PanOSSourceDeviceOSFamily= PanOSSourceDeviceOSVersion= PanOSSourceDeviceHost= PanOSSourceDeviceMac= PanOSDestinationDeviceCategory= PanOSDestinationDeviceProfile= PanOSDestinationDeviceModel= PanOSDestinationDeviceVendor= PanOSDestinationDeviceOSFamily= PanOSDestinationDeviceOSVersion= PanOSDestinationDeviceHost= PanOSDestinationDeviceMac= PanOSContainerID= PanOSContainerNameSpace= PanOSContainerName= PanOSSourceEDL= PanOSDestinationEDL= PanOSHostID=xxxxxxxxxxxxxx PanOSEndpointSerialNumber=xxxxxxxxxxxxxx PanOSDomainEDL= PanOSSourceDynamicAddressGroup= PanOSDestinationDynamicAddressGroup= PanOSPartialHash= PanOSTimeGeneratedHighResolution=Jul 25 2019 23:30:12 PanOSReasonForDataFilteringAction= PanOSJustification= PanOSNSSAINetworkSliceType=",
        "event": {
            "severity": 3,
            "action": "alert",
            "timezone": "UTC",
            "start": "2021-03-01T21:06:06.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "THREAT"
        },
        "network": {
            "protocol": "smtp"
        },
        "source": {
            "ip": "1.1.1.1",
            "port": 37404,
            "address": "1.1.1.1"
        },
        "destination": {
            "port": 25,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "file": {
            "inode": "0",
            "path": "page-icon.png"
        },
        "@timestamp": "2021-03-01T21:06:06.000000Z",
        "cef": {
            "externalId": "xxxxxxxxxxxxx",
            "flexString2Label": "DirectionOfAttack",
            "flexString2": "client to server",
            "cs2Label": "URLCategory",
            "cs2": "any",
            "dpt": "25",
            "cnt": 9,
            "cn1Label": "SessionID",
            "cn1": 4016143,
            "cs6Label": "LogSetting",
            "cs6": "test",
            "cs5Label": "ToZone",
            "cs5": "tap",
            "cs4Label": "FromZone",
            "cs4": "tap",
            "cs3Label": "VirtualLocation",
            "cs3": "smtp",
            "cs1Label": "Rule",
            "cs1": "dg-log-policy",
            "rt": "Mar 01 2021 21:06:06",
            "Name": "file"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_globalprotect_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|GLOBALPROTECT|globalprotect|3|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 20:35:54 PanOSDeviceSN=xxxxxxxxxxxxx PanOSConfigVersion= start=Mar 01 2021 20:35:54 PanOSVirtualSystem=vsys1 PanOSEventIDValue=satellite-gateway-update-route PanOSStage=connected PanOSAuthMethod=RADIUS PanOSTunnelType=ipsec PanOSSourceUserName=xxxxx\\\\\\\\xxxxx PanOSSourceRegion=ET PanOSEndpointDeviceName=machine_name2 PanOSPublicIPv4=1.1.1.1 PanOSPublicIPv6=xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx PanOSPrivateIPv4=1.1.1.1 PanOSPrivateIPv6=xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx PanOSHostID=xxxxxxxxxxxxxxe667947f-d92e-4815-9222-89438203bc2b PanOSEndpointSN=serialno_list-1 PanOSGlobalProtectClientVersion=3.0.9 PanOSEndpointOSType=Intel Mac OS PanOSEndpointOSVersion=9.3.5 PanOSCountOfRepeats=16777216 PanOSQuarantineReason=Malicious Traffic PanOSConnectionError=Client cert not present PanOSDescription=opaque_list-1 PanOSEventStatus=failure PanOSGlobalProtectGatewayLocation=San Francisco PanOSLoginDuration=1 PanOSConnectionMethod=connect_method_list-1 PanOSConnectionErrorID=0 PanOSPortal=portal_list-2 PanOSSequenceNo=34401910 PanOSTimeGeneratedHighResolution=Jul 25 2019 23:30:12 PanOSGatewaySelectionType= PanOSSSLResponseTime= PanOSGatewayPriority= PanOSAttemptedGateways= PanOSGateway= PanOSDGHierarchyLevel1=20 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= PanOSDeviceName=PA-VM PanOSVirtualSystemID=1",
        "event": {
            "severity": 3,
            "timezone": "UTC",
            "start": "2021-03-01T20:35:54.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "GLOBALPROTECT"
        },
        "@timestamp": "2021-03-01T20:35:54.000000Z",
        "cef": {
            "rt": "Mar 01 2021 20:35:54",
            "Name": "globalprotect"
        }
    }
    	
	```


=== "pan_ngfw_hip_match_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|HIPMATCH||3|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 21:20:13 deviceExternalId=xxxxxxxxxxxxx PanOSIsDuplicateLog=false PanOSIsPrismaNetworks=false PanOSIsPrismaUsers=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSSourceDeviceClass= PanOSSourceDeviceOS= sntdom=xxxxx dntdom=xxxxx suser=xxxxx xxxxx duser=xxxxx xxxxx suid= duid= PanOSTenantID=xxxxxxxxxxxxx PanOSUUID= PanOSConfigVersion= start=Mar 01 2021 21:20:13 PanOSSourceUser=xxxxx\\\\xxxxx xxxxx cs3=vsys1 cs3Label=VirtualLocation shost=machine_name1 dhost=machine_name1 cs2=iOS cs2Label=EndpointOSType src=1.1.1.1 dst=1.1.1.1 cat=match_name1 cnt=1 PanOSHipMatchType=HIP Profile externalId=xxxxxxxxxxxxx PanOSDGHierarchyLevel1=12 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=PA-5220 cn2=1 cn2Label=VirtualSystemID c6a1=xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx c6a1Label=Device IPv6 Address PanOSHostID=xxxxxxxxxxxxxxe777947f-d92e-4815-9222-89438203bc2b PanOSEndpointSerialNumber=xxxxxxxxxxxxxx PanOSSourceDeviceCategory= PanOSSourceDeviceProfile= PanOSSourceDeviceModel= PanOSSourceDeviceVendor= PanOSSourceDeviceOSFamily= PanOSSourceDeviceOSVersion= PanOSSourceDeviceMac= PanOSSourceDeviceHost= PanOSSource= PanOSTimestampDeviceIdentification=Dec PanOSTimeGeneratedHighResolution=Jul 25 2019 23:30:12",
        "event": {
            "severity": 3,
            "timezone": "UTC",
            "start": "2021-03-01T21:20:13.000000Z"
        },
        "@timestamp": "2021-03-01T21:20:13.000000Z",
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "HIPMATCH"
        },
        "source": {
            "ip": "1.1.1.1",
            "user": {
                "name": "xxxxx xxxxx"
            },
            "address": "1.1.1.1"
        },
        "destination": {
            "domain": "machine_name1",
            "ip": "1.1.1.1",
            "user": {
                "name": "xxxxx xxxxx"
            },
            "address": "machine_name1"
        },
        "host": {
            "hostname": "machine_name1",
            "name": "machine_name1"
        },
        "cef": {
            "c6a1Label": "Device IPv6 Address",
            "c6a1": "xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx:xxxx",
            "cn2Label": "VirtualSystemID",
            "cn2": 1,
            "externalId": "xxxxxxxxxxxxx",
            "cnt": 1,
            "cat": "match_name1",
            "cs2Label": "EndpointOSType",
            "cs2": "iOS",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "sntdom": "xxxxx",
            "rt": "Mar 01 2021 21:20:13",
            "Name": ""
        },
        "related": {
            "hosts": [
                "machine_name1"
            ],
            "user": [
                "xxxxx xxxxx"
            ],
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_iptag_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|IPTAG|iptag|3|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 21:20:13 deviceExternalId=xxxxxxxxxxxxx PanOSTenantID=xxxxxxxxxxxxx PanOSIsDuplicateLog=false PanOSIsPrismaNetworks=false PanOSIsPrismaUsers=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSetting= PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSRuleMatched= PanOSRuleMatchedUUID= PanOSConfigVersion= start=Mar 01 2021 21:20:13 cs3=vsys1 cs3Label=VirtualLocation src=1.1.1.1 dst=1.1.1.1 PanOSTagName= PanOSEventID=Unregister cnt=1 PanOSMappingTimeout=10 PanOSMappingDataSource=XMLAPI PanOSMappingDataSourceType=XML-API PanOSMappingDataSourceSubType=Unknown externalId=xxxxxxxxxxxxx PanOSDGHierarchyLevel1=18 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=PA-VM cn2=1 cn2Label=VirtualSystemID PanOSIPSubnetRange= PanOSTimeGeneratedHighResolution=Jul 25 2019 23:30:12",
        "event": {
            "severity": 3,
            "timezone": "UTC",
            "start": "2021-03-01T21:20:13.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "IPTAG"
        },
        "source": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "destination": {
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "@timestamp": "2021-03-01T21:20:13.000000Z",
        "cef": {
            "cn2Label": "VirtualSystemID",
            "cn2": 1,
            "externalId": "xxxxxxxxxxxxx",
            "cnt": 1,
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "rt": "Mar 01 2021 21:20:13",
            "Name": "iptag"
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_sctp_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|SCTP||9|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 21:22:02 deviceExternalId=xxxxxxxxxxxxx PanOSCaptivePortal= PanOSContentVersion= PanOSCortexDataLakeTenantID=xxxxxxxxxxxxx PanOSDestinationDeviceClass= PanOSDestinationDeviceMac= PanOSDestinationDeviceModel= PanOSDestinationDeviceOS= PanOSDestinationDeviceVendor= PanOSDestinationLocation=IN PanOSDestinationUUID= PanOSDestinationUserDomain=paloaltonetwork PanOSDestinationUserName=xxxxx PanOSDestinationUserUUID= PanOSInboundInterfaceDetailsPort=1 PanOSInboundInterfaceDetailsSlot=1 PanOSInboundInterfaceDetailsType=ethernet PanOSInboundInterfaceDetailsUnit=0 PanOSIsClienttoServer= PanOSIsContainer= PanOSIsDecryptMirror= PanOSIsDecryptedLog= PanOSIsDecryptedPayloadForward= PanOSIsDuplicateLog=false PanOSIsIPV6= PanOSIsInspectrionBeforeSession= PanOSIsMptcpOn= PanOSIsNonStandardDestinationPort= PanOSIsPacketCapture= PanOSIsPhishing= PanOSIsPrismaNetwork=false PanOSIsPrismaUsers=false PanOSIsProxy= PanOSIsReconExcluded= PanOSIsServertoClient= PanOSIsSourceXForwarded= PanOSIsSystemReturn= PanOSIsTransaction= PanOSIsTunnelInspected= PanOSIsURLDenied= PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSNAT= PanOSOutboundInterfaceDetailsPort=2 PanOSOutboundInterfaceDetailsSlot=1 PanOSOutboundInterfaceDetailsType=ethernet PanOSOutboundInterfaceDetailsUnit=0 PanOSSessionEndReason= PanOSSessionOwnerMidx= PanOSSessionTracker= PanOSSeverity=Critical PanOSSourceDeviceClass= PanOSSourceDeviceMac= PanOSSourceDeviceModel= PanOSSourceDeviceOS= PanOSSourceDeviceVendor= PanOSSourceLocation=US PanOSSourceUUID= PanOSSourceUserDomain=paloaltonetwork PanOSSourceUserName=xxxxx PanOSSourceUserUUID= PanOSTunnel=N/A PanOSVirtualSystemID=1 PanOSConfigVersion= start=Mar 01 2021 21:22:02 src=1.1.1.1 dst=1.1.1.1 PanOSNATSource=1.1.1.1 PanOSNATDestination=1.1.1.1 cs1=allow-business-apps cs1Label=Rule PanOSSourceUser=paloaltonetwork\\\\xxxxx PanOSDestinationUser=paloaltonetworkxxxxx PanOSApplication=panorama cs3=vsys1 cs3Label=VirtualLocation cs4=corporate cs4Label=FromZone cs5=untrust cs5Label=ToZone PanOSInboundInterface=ethernet1/1 deviceOutboundInterface=ethernet1/2 cs6=test cs6Label=LogSetting PanOSSessionID=391582 cnt=1 spt=3033 dpt=5496 PanOSNATSourcePort=26714 PanOSNATDestinationPort=15054 proto=tcp act=alert PanOSDGHierarchyLevel1=12 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=PA-5220 externalId=xxxxxxxxxxxxx PanOSEndpointAssociationID=2086888838 PanOSPayloadProtocolID=-1 PanOSSctpChunkType=9 PanOSSCTPEventType=Kerberos single sign-on failed PanOSEventCode=3 PanOSVerificationTag1=0x3bae3042 PanOSVerificationTag2=0x1911015e PanOSSctpCauseCode=0 PanOSDiamAppID=-1 PanOSDiameterCommandCode=-1 PanOSDiamAvpCode=0 PanOSStreamID=0 PanOSAssocationEndReason= PanOSMapAppCode=0 PanOSSccpCallingSSN=0 PanOSSccpCallingGt= PanOSSctpFilter= PanOSChunksTotal=0 PanOSChunksSent=0 PanOSChunksReceived=0 PanOSPacketsTotal=0 PanOSPacketsSent=0 PanOSPacketsReceived=0 PanOSRuleUUID= PanOSContainerID= PanOSContainerNameSpace= PanOSContainerName= PanOSSourceEDL= PanOSDestinationEDL= PanOSSourceDynamicAddressGroup= PanOSDestinationDynamicAddressGroup= PanOSTimeGeneratedHighResolution=Jul 25 2019 23:30:12",
        "event": {
            "severity": 9,
            "action": "alert",
            "timezone": "UTC",
            "start": "2021-03-01T21:22:02.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "SCTP"
        },
        "source": {
            "ip": "1.1.1.1",
            "port": 3033,
            "address": "1.1.1.1"
        },
        "destination": {
            "port": 5496,
            "ip": "1.1.1.1",
            "address": "1.1.1.1"
        },
        "@timestamp": "2021-03-01T21:22:02.000000Z",
        "cef": {
            "externalId": "xxxxxxxxxxxxx",
            "dpt": "5496",
            "cnt": 1,
            "cs6Label": "LogSetting",
            "cs6": "test",
            "cs5Label": "ToZone",
            "cs5": "untrust",
            "cs4Label": "FromZone",
            "cs4": "corporate",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "cs1Label": "Rule",
            "cs1": "allow-business-apps",
            "rt": "Mar 01 2021 21:22:02",
            "Name": ""
        },
        "related": {
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_threat_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|THREAT|spyware|1|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 20:48:21 deviceExternalId=xxxxxxxxxxxxx start=Mar 01 2021 20:48:16 PanOSApplicationCategory=general-internet PanOSApplicationContainer=sina-weibo PanOSApplicationRisk=4 PanOSApplicationSubcategory=social-networking PanOSApplicationTechnology=browser-based PanOSCaptivePortal=false PanOSCloudHostname=xxxxx PanOSCortexDataLakeTenantID=xxxxxxxxxxxxx PanOSDestinationDeviceClass= PanOSDestinationDeviceOS= dntdom=paloaltonetwork duser=xxxxx duid= PanOSHTTPMethod=get PanOSInboundInterfaceDetailsPort=0 PanOSInboundInterfaceDetailsSlot=0 PanOSInboundInterfaceDetailsType=unknown PanOSInboundInterfaceDetailsUnit=0 PanOSIsClienttoServer=true PanOSIsContainer=false PanOSIsDecryptMirror=false PanOSIsDecrypted=false PanOSIsDuplicateLog=false PanOSIsEncrypted=false PanOSIsIPV6=false PanOSIsMptcpOn=false PanOSIsNonStandardDestinationPort=false PanOSIsPacketCapture=false PanOSIsPhishing=false PanOSIsPrismaNetwork=false PanOSIsPrismaUsers=false PanOSIsProxy=false PanOSIsReconExcluded=false PanOSIsSaaSApplication=false PanOSIsServertoClient=false PanOSIsSourceXForwarded=true PanOSIsSystemReturn=true PanOSIsTransaction=false PanOSIsTunnelInspected=false PanOSIsURLDenied=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSNAT=false PanOSNonStandardDestinationPort=13884 PanOSOutboundInterfaceDetailsPort=0 PanOSOutboundInterfaceDetailsSlot=0 PanOSOutboundInterfaceDetailsType=unknown PanOSOutboundInterfaceDetailsUnit=0 PanOSPacket= PanOSPayloadProtocolID=-1 PanOSSanctionedStateOfApp=false PanOSSeverity=Informational PanOSSourceDeviceClass= PanOSSourceDeviceOS= sntdom=paloaltonetwork suser=xxxxx suid= cat=27379 PanOSThreatNameFirewall=27379 PanOSTunneledApplication=tunneled-app PanOSURLDomain= PanOSUsers=paloaltonetwork\\\\xxxxx PanOSVerdict= PanOSVirtualSystemID=1 c6a2=fe80:110:8897:efab:9202:b3ff:fe1e:8329 c6a2Label=Source IPv6 Address c6a3=fe80:110:8897:efab:9202:b3ff:fe1e:8329 c6a3Label=Destination IPv6 Address sourceTranslatedAddress=1.1.1.1 destinationTranslatedAddress=1.1.1.1 cs1=deny-attackers cs1Label=Rule suser0=paloaltonetwork\\\\xxxxx duser0=paloaltonetwork\\\\xxxxx app=sina-weibo-base cs3=vsys1 cs3Label=VirtualLocation cs4=datacenter cs4Label=FromZone cs5=ethernet4Zone-test4 cs5Label=ToZone deviceInboundInterface=unknown deviceOutboundInterface=unknown cs6=rs-logging cs6Label=LogSetting cn1=947181 cn1Label=SessionID cnt=1 spt=13884 dpt=4228 sourceTranslatedPort=30116 destinationTranslatedPort=20966 proto=tcp act=drop-all request=some other fake filename PanOSThreatID=27379(27379) flexString2=server to client flexString2Label=DirectionOfAttack externalId=xxxxxxxxxxxxx PanOSSourceLocation=LY PanOSDestinationLocation=BR fileId=0 PanOSFileHash= PanOSApplianceOrCloud= PanOSURLCounter=0 PanOSFileType= PanOSSenderEmail= PanOSEmailSubject= PanOSRecipientEmail= PanOSReportID=0 PanOSDGHierarchyLevel1=11 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=xxxxx PanOSSourceUUID= PanOSDestinationUUID= PanOSIMSI=0 PanOSIMEI= PanOSParentSessionID=0 PanOSParentStarttime=Jan 01 1970 00:00:00 PanOSTunnel=N/A PanOSThreatCategory=unknown PanOSContentVersion=50059 PanOSSigFlags=0x0 PanOSRuleUUID=017e4d76-2003-47f4-8afc-1d35c808c615 PanOSHTTP2Connection=0 PanOSDynamicUserGroupName= PanOSX-Forwarded-ForIP= PanOSSourceDeviceCategory=X-Phone PanOSSourceDeviceProfile=x-profile PanOSSourceDeviceModel=Note 4G PanOSSourceDeviceVendor=Lenovo PanOSSourceDeviceOSFamily=K6 PanOSSourceDeviceOSVersion=Android v9 PanOSSourceDeviceHost=pan-505 PanOSSourceDeviceMac=596703749274 PanOSDestinationDeviceCategory=X-Phone PanOSDestinationDeviceProfile=x-profile PanOSDestinationDeviceModel=MI PanOSDestinationDeviceVendor=Xiaomi PanOSDestinationDeviceOSFamily=A1 PanOSDestinationDeviceOSVersion=Android v9.1 PanOSDestinationDeviceHost=pan-622 PanOSDestinationDeviceMac=620797415366 PanOSContainerID=1873cc5c-0d31 PanOSContainerNameSpace=pns_default PanOSSourceEDL= PanOSDestinationEDL= PanOSHostID=xxxxxxxxxxxxxx PanOSEndpointSerialNumber=xxxxxxxxxxxxxx PanOSDomainEDL= PanOSSourceDynamicAddressGroup= PanOSDestinationDynamicAddressGroup= PanOSPartialHash=0 PanOSTimeGeneratedHighResolution=Mar 01 2021 20:48:16 PanOSNSSAINetworkSliceType=dc",
        "event": {
            "severity": 1,
            "action": "drop-all",
            "timezone": "UTC",
            "start": "2021-03-01T20:48:16.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "THREAT"
        },
        "network": {
            "protocol": "sina-weibo-base"
        },
        "source": {
            "user": {
                "name": "xxxxx"
            },
            "port": 13884
        },
        "destination": {
            "domain": "paloaltonetwork",
            "port": 4228,
            "user": {
                "name": "xxxxx"
            },
            "address": "paloaltonetwork"
        },
        "file": {
            "inode": "0"
        },
        "url": {
            "original": "some other fake filename",
            "path": "some other fake filename"
        },
        "@timestamp": "2021-03-01T20:48:16.000000Z",
        "cef": {
            "externalId": "xxxxxxxxxxxxx",
            "flexString2Label": "DirectionOfAttack",
            "flexString2": "server to client",
            "dpt": "4228",
            "cnt": 1,
            "cn1Label": "SessionID",
            "cn1": 947181,
            "cs6Label": "LogSetting",
            "cs6": "rs-logging",
            "cs5Label": "ToZone",
            "cs5": "ethernet4Zone-test4",
            "cs4Label": "FromZone",
            "cs4": "datacenter",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "cs1Label": "Rule",
            "cs1": "deny-attackers",
            "c6a3Label": "Destination IPv6 Address",
            "c6a3": "fe80:110:8897:efab:9202:b3ff:fe1e:8329",
            "c6a2Label": "Source IPv6 Address",
            "c6a2": "fe80:110:8897:efab:9202:b3ff:fe1e:8329",
            "cat": "27379",
            "sntdom": "paloaltonetwork",
            "rt": "Mar 01 2021 20:48:21",
            "Name": "spyware"
        },
        "related": {
            "user": [
                "xxxxx"
            ],
            "hosts": [
                "paloaltonetwork"
            ]
        }
    }
    	
	```


=== "pan_ngfw_traffic_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|TRAFFIC|end|3|ProfileToken=xxxxx dtz=UTC rt=Feb 27 2021 20:16:21 deviceExternalId=xxxxxxxxxxxxx PanOSApplicationContainer= PanOSApplicationRisk=5 PanOSApplicationSubcategory=file-sharing PanOSApplicationTechnology=peer-to-peer PanOSCaptivePortal=false PanOSCortexDataLakeTenantID=xxxxxxxxxxxxx PanOSDestinationDeviceClass= PanOSDestinationDeviceOS= dntdom=paloaltonetwork duser=xxxxx duid= PanOSInboundInterfaceDetailsPort=0 PanOSInboundInterfaceDetailsSlot=0 PanOSInboundInterfaceDetailsType=unknown PanOSInboundInterfaceDetailsUnit=0 PanOSIsClienttoServer=false PanOSIsContainer=false PanOSIsDecryptMirror=false PanOSIsDecrypted=false PanOSIsDecryptedLog=false PanOSIsDecryptedPayloadForward=false PanOSIsDuplicateLog=false PanOSIsEncrypted=false PanOSIsIPV6=false PanOSIsInspectionBeforeSession=true PanOSIsMptcpOn=false PanOSIsNonStandardDestinationPort=false PanOSIsPacketCapture=false PanOSIsPhishing=false PanOSIsPrismaNetwork=false PanOSIsPrismaUsers=false PanOSIsProxy=false PanOSIsReconExcluded=false PanOSIsSaaSApplication=false PanOSIsServertoClient=false PanOSIsSourceXForwarded=false PanOSIsSystemReturn=false PanOSIsTransaction=false PanOSIsTunnelInspected=false PanOSIsURLDenied=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSNAT=false PanOSNonStandardDestinationPort=0 PanOSOutboundInterfaceDetailsPort=0 PanOSOutboundInterfaceDetailsSlot=0 PanOSOutboundInterfaceDetailsType=unknown PanOSOutboundInterfaceDetailsUnit=0 PanOSSDWANFECRatio=0.0 PanOSSanctionedStateOfApp=false PanOSSessionOwnerMidx=false PanOSSessionTracker=16 PanOSSourceDeviceClass= PanOSSourceDeviceOS= sntdom=xxxxx suser=xxxxx xxxxx suid= PanOSTunneledApplication=tunneled-app PanOSUsers=xxxxx\\\\xxxxx xxxxx PanOSVirtualSystemID=1 PanOSApplicationCategory=peer2peer PanOSConfigVersion=10.0 start=Feb 27 2021 20:16:17 src=1.1.1.1 dst=1.1.1.1 sourceTranslatedAddress=1.1.1.1 destinationTranslatedAddress=1.1.1.1 cs1=deny-attackers cs1Label=Rule suser0=xxxxx\\\\xxxxx xxxxx duser0=paloaltonetwork\\\\xxxxx app=fileguri cs3=vsys1 cs3Label=VirtualLocation cs4=untrust cs4Label=FromZone cs5=ethernet4Zone-test1 cs5Label=ToZone deviceInboundInterface=unknown deviceOutboundInterface=unknown cs6=rs-logging cs6Label=LogSetting cn1=25596 cn1Label=SessionID cnt=1 spt=22871 dpt=27092 sourceTranslatedPort=24429 destinationTranslatedPort=14744 proto=tcp act=deny PanOSBytes=1370294 out=400448 in=969846 cn2=314 cn2Label=PacketsTotal PanOSSessionStartTime=Feb 27 2021 20:15:48 cn3=56 cn3Label=SessionDuration cs2=custom-category cs2Label=URLCategory externalId=xxxxxxxxxxxxx PanOSSourceLocation=east-coast PanOSDestinationLocation=BR PanOSPacketsSent=194 PanOSPacketsReceived=120 reason=unknown PanOSDGHierarchyLevel1=11 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=xxxxx cat=unknown PanOSSourceUUID= PanOSDestinationUUID= PanOSIMSI=0 PanOSIMEI= PanOSParentSessionID=0 PanOSParentStarttime=Feb 27 2021 20:15:40 PanOSTunnel=GRE PanOSEndpointAssociationID=-3746994889972252628 PanOSChunksTotal=1945 PanOSChunksSent=323 PanOSChunksReceived=1622 PanOSRuleUUID=017e4d76-2003-47f4-8afc-1d35c808c615 PanOSHTTP2Connection=469139 PanOSLinkChangeCount=0 PanOSSDWANPolicyName= PanOSLinkSwitches= PanOSSDWANCluster= PanOSSDWANDeviceType= PanOSSDWANClusterType= PanOSSDWANSite= PanOSDynamicUserGroupName=dynug-4 PanOSX-Forwarded-ForIP=1.1.1.1 PanOSSourceDeviceCategory=N-Phone PanOSSourceDeviceProfile=n-profile PanOSSourceDeviceModel=Nexus PanOSSourceDeviceVendor=Google PanOSSourceDeviceOSFamily=LG-H790 PanOSSourceDeviceOSVersion=Android v6 PanOSSourceDeviceHost=pan-301 PanOSSourceDeviceMac=839147449905 PanOSDestinationDeviceCategory=N-Phone PanOSDestinationDeviceProfile=n-profile PanOSDestinationDeviceModel=Nexus PanOSDestinationDeviceVendor=Google PanOSDestinationDeviceOSFamily=H1511 PanOSDestinationDeviceOSVersion=Android v7 PanOSDestinationDeviceHost=pan-355 PanOSDestinationDeviceMac=530589561221 PanOSContainerID=1873cc5c-0d31 PanOSContainerNameSpace=pns_default PanOSContainerName=pan-dp-77754f4 PanOSSourceEDL= PanOSDestinationEDL= PanOSGPHostID=xxxxxxxxxxxxxx PanOSEndpointSerialNumber=xxxxxxxxxxxxxx PanOSSourceDynamicAddressGroup= aqua_dag PanOSDestinationDynamicAddressGroup= PanOSHASessionOwner=session_owner-4 PanOSTimeGeneratedHighResolution=Feb 27 2021 20:16:18 PanOSNSSAINetworkSliceType=0 PanOSNSSAINetworkSliceDifferentiator=1bca5",
        "event": {
            "severity": 3,
            "action": "unknown",
            "timezone": "UTC",
            "start": "2021-02-27T20:16:17.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "TRAFFIC"
        },
        "network": {
            "protocol": "fileguri"
        },
        "source": {
            "ip": "1.1.1.1",
            "user": {
                "name": "xxxxx xxxxx"
            },
            "port": 22871,
            "address": "1.1.1.1"
        },
        "destination": {
            "domain": "paloaltonetwork",
            "port": 27092,
            "ip": "1.1.1.1",
            "user": {
                "name": "xxxxx"
            },
            "address": "paloaltonetwork"
        },
        "host": {
            "network": {
                "ingress": {
                    "bytes": 969846
                },
                "egress": {
                    "bytes": 400448
                }
            }
        },
        "@timestamp": "2021-02-27T20:16:17.000000Z",
        "cef": {
            "cat": "unknown",
            "externalId": "xxxxxxxxxxxxx",
            "cs2Label": "URLCategory",
            "cs2": "custom-category",
            "cn3": 56,
            "cn2Label": "PacketsTotal",
            "cn2": 314,
            "dpt": "27092",
            "cnt": 1,
            "cn1Label": "SessionID",
            "cn1": 25596,
            "cs6Label": "LogSetting",
            "cs6": "rs-logging",
            "cs5Label": "ToZone",
            "cs5": "ethernet4Zone-test1",
            "cs4Label": "FromZone",
            "cs4": "untrust",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "cs1Label": "Rule",
            "cs1": "deny-attackers",
            "sntdom": "xxxxx",
            "rt": "Feb 27 2021 20:16:21",
            "Name": "end"
        },
        "related": {
            "user": [
                "xxxxx",
                "xxxxx xxxxx"
            ],
            "hosts": [
                "paloaltonetwork"
            ],
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_url_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|THREAT|url|1|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 20:48:21 deviceExternalId=xxxxxxxxxxxxx PanOSApplicationCategory=database PanOSApplicationContainer= PanOSApplicationRisk=2 PanOSApplicationSubcategory=database PanOSApplicationTechnology=client-server PanOSCaptivePortal=false PanOSCloudHostname=xxxxx PanOSCortexDataLakeTenantID=xxxxxxxxxxxxx PanOSDestinationDeviceClass= PanOSDestinationDeviceOS= dntdom=xxxxx duser=xxxxx o\"'\"test duid= PanOSHTTPRefererFQDN= PanOSHTTPRefererPort= PanOSHTTPRefererProtocol= PanOSHTTPRefererURLPath= PanOSInboundInterfaceDetailsPort=0 PanOSInboundInterfaceDetailsSlot=0 PanOSInboundInterfaceDetailsType=unknown PanOSInboundInterfaceDetailsUnit=0 PanOSIsClienttoServer=true PanOSIsContainer=false PanOSIsDecryptMirror=false PanOSIsDecrypted=false PanOSIsDuplicateLog=false PanOSIsEncrypted=false PanOSIsIPV6=false PanOSIsMptcpOn=false PanOSIsNonStandardDestinationPort=false PanOSIsPacketCapture=false PanOSIsPhishing=false PanOSIsPrismaNetwork=false PanOSIsPrismaUsers=false PanOSIsProxy=false PanOSIsReconExcluded=false PanOSIsSaaSApplication=false PanOSIsServertoClient=false PanOSIsSourceXForwarded=true PanOSIsSystemReturn=true PanOSIsTransaction=false PanOSIsTunnelInspected=false PanOSIsURLDenied=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSNAT=false PanOSNonStandardDestinationPort=32350 PanOSOutboundInterfaceDetailsPort=2 PanOSOutboundInterfaceDetailsSlot=1 PanOSOutboundInterfaceDetailsType=ethernet PanOSOutboundInterfaceDetailsUnit=0 PanOSPacket= PanOSSanctionedStateofApp=false PanOSSeverity=Informational PanOSSourceDeviceClass= PanOSSourceDeviceOS= sntdom=xxxxx suser=xxxxx xxxxx suid= PanOSTunneledApplication=untunneled PanOSURLDomain=?% PanOSUsers=xxxxx\\\\xxxxx xxxxx PanOSVirtualSystemID=1 PanOSConfigVersion=10.0 start=Mar 01 2021 20:48:16 src=1.1.1.1 dst=1.1.1.1 sourceTranslatedAddress=1.1.1.1 destinationTranslatedAddress=1.1.1.1 cs1=allow-business-apps cs1Label=Rule suser0=xxxxx\\\\xxxxx xxxxx duser0=xxxxx\\\\xxxxx o\"'\"test app=maxdb cs3=vsys1 cs3Label=VirtualLocation cs4=ethernet4Zone-test4 cs4Label=FromZone cs5=untrust cs5Label=ToZone deviceInboundInterface=unknown deviceOutboundInterface=ethernet1/2 cs6=rs-logging cs6Label=LogSetting cn1=980296 cn1Label=SessionID cnt=1 spt=32350 dpt=1532 sourceTranslatedPort=26236 destinationTranslatedPort=12016 proto=tcp act=block-url request=?% cs2=sports cs2Label=URLCategory flexString2=server to client flexString2Label=DirectionOfAttack externalId=xxxxxxxxxxxxx PanOSSourceLocation=west-coast PanOSDestinationLocation=PK requestContext=application/jpeg fileId=0 PanOSURLCounter=1 requestClientApplication= PanOSX-Forwarded-For= PanOSReferer= PanOSDGHierarchyLevel1=11 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=xxxxx PanOSSourceUUID= PanOSDestinationUUID= requestMethod=post PanOSIMSI=1 PanOSIMEI=Navy Base PanOSParentSessionID=8802 PanOSParentStarttime=Mar 01 2021 20:48:10 PanOSTunnel=VXLAN PanOSInlineMLVerdict=overflow PanOSContentVersion=50222 PanOSSigFlags=2 PanOSHTTPHeaders= PanOSURLCategoryList=sports,\u200b11008,\u200b38340 PanOSRuleUUID=ec14df0b-c845-4435-87a2-d207730f5ae8 PanOSHTTP2Connection=8802 PanOSDynamicUserGroupName= PanOSX-Forwarded-ForIP= PanOSSourceDeviceCategory=L-Phone PanOSSourceDeviceProfile=l-profile PanOSSourceDeviceModel=Note 4G PanOSSourceDeviceVendor=Lenovo PanOSSourceDeviceOSFamily=K6 PanOSSourceDeviceOSVersion=Android v9 PanOSSourceDeviceHost=pan-505 PanOSSourceDeviceMac=596703749274 PanOSDestinationDeviceCategory=L-Phone PanOSDestinationDeviceProfile=l-profile PanOSDestinationDeviceModel=Note XT PanOSDestinationDeviceVendor=Lenovo PanOSDestinationDeviceOSFamily=K8 PanOSDestinationDeviceOSVersion=Android v8 PanOSDestinationDeviceHost=pan-506 PanOSDestinationDeviceMac=150083646537 PanOSContainerID=1873cc5c-0d31 PanOSContainerNameSpace=pns_default PanOSContainerName=pan-dp-77754f4 PanOSSourceEDL= PanOSDestinationEDL= PanOSHostID=xxxxxxxxxxxxxx PanOSEndpointSerialNumber=xxxxxxxxxxxxxx PanOSSourceDynamicAddressGroup= blue_dag PanOSDestinationDynamicAddressGroup= PanOSTimeGeneratedHighResolution=Mar 01 2021 20:48:16 PanOSNSSAINetworkSliceType=b5",
        "event": {
            "severity": 1,
            "action": "block-url",
            "timezone": "UTC",
            "start": "2021-03-01T20:48:16.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "THREAT"
        },
        "network": {
            "protocol": "maxdb"
        },
        "source": {
            "ip": "1.1.1.1",
            "user": {
                "name": "xxxxx xxxxx"
            },
            "port": 32350,
            "address": "1.1.1.1"
        },
        "destination": {
            "domain": "xxxxx",
            "port": 1532,
            "ip": "1.1.1.1",
            "user": {
                "name": "xxxxx o\"'\"test"
            },
            "address": "xxxxx"
        },
        "file": {
            "inode": "0"
        },
        "url": {
            "original": "?%",
            "query": "%"
        },
        "http": {
            "request": {
                "referrer": "application/jpeg",
                "method": "post"
            }
        },
        "@timestamp": "2021-03-01T20:48:16.000000Z",
        "cef": {
            "externalId": "xxxxxxxxxxxxx",
            "flexString2Label": "DirectionOfAttack",
            "flexString2": "server to client",
            "cs2Label": "URLCategory",
            "cs2": "sports",
            "dpt": "1532",
            "cnt": 1,
            "cn1Label": "SessionID",
            "cn1": 980296,
            "cs6Label": "LogSetting",
            "cs6": "rs-logging",
            "cs5Label": "ToZone",
            "cs5": "untrust",
            "cs4Label": "FromZone",
            "cs4": "ethernet4Zone-test4",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "cs1Label": "Rule",
            "cs1": "allow-business-apps",
            "sntdom": "xxxxx",
            "rt": "Mar 01 2021 20:48:21",
            "Name": "url"
        },
        "related": {
            "user": [
                "xxxxx o\"'\"test",
                "xxxxx xxxxx"
            ],
            "hosts": [
                "xxxxx"
            ],
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```


=== "pan_ngfw_userid_cef.json"

    ```json
	
    {
        "message": "CEF:0|Palo Alto Networks|LF|2.0|USERID|logout|3|ProfileToken=xxxxx dtz=UTC rt=Mar 01 2021 21:06:02 deviceExternalId=xxxxxxxxxxxxx PanOSConfigVersion= dntdom=paloaltonetwork duser=xxxxx duid= PanOSCortexDataLakeTenantID=xxxxxxxxxxxxx PanOSIsDuplicateLog=false PanOSIsDuplicateUser= PanOSIsPrismaNetworks=false PanOSIsPrismaUsers=false PanOSLogExported=false PanOSLogForwarded=true PanOSLogSource=firewall PanOSLogSourceTimeZoneOffset= PanOSUserGroupFound= start=Mar 01 2021 21:06:02 cs3=vsys1 cs3Label=VirtualLocation src=1.1.1.1 dst=1.1.1.1 duser0=paloaltonetworks\\\\xxxxx cs4=fake-data-source-169 cs4Label=MappingDataSourceName cat=0 cnt=1 cn3=3531 cn3Label=MappingTimeout spt=21015 dpt=49760 cs5=probing cs5Label=MappingDataSource cs6=netbios_probing cs6Label=MappingDataSourceType externalId=xxxxxxxxxxxxx PanOSDGHierarchyLevel1=12 PanOSDGHierarchyLevel2=0 PanOSDGHierarchyLevel3=0 PanOSDGHierarchyLevel4=0 PanOSVirtualSystemName= dvchost=PA-5220 cn2=1 cn2Label=VirtualSystemID cs1=xxxxx cs1Label=MFAFactorType end=Jul 09 2019 18:15:44 cn1=3 cn1Label=AuthFactorNo PanOSUGFlags=0x100 PanOSUserIdentifiedBySource=xxxxxxxxxxxxxx PanOSTag= PanOSTimeGeneratedHighResolution=Jul 25 2019 23:30:12",
        "event": {
            "severity": 3,
            "timezone": "UTC",
            "end": "2019-07-09T18:15:44.000000Z",
            "start": "2021-03-01T21:06:02.000000Z"
        },
        "observer": {
            "vendor": "Palo Alto Networks",
            "type": "LF",
            "version": "2.0"
        },
        "rule": {
            "id": "USERID"
        },
        "source": {
            "ip": "1.1.1.1",
            "port": 21015,
            "address": "1.1.1.1"
        },
        "destination": {
            "domain": "paloaltonetwork",
            "port": 49760,
            "ip": "1.1.1.1",
            "user": {
                "name": "xxxxx"
            },
            "address": "paloaltonetwork"
        },
        "@timestamp": "2021-03-01T21:06:02.000000Z",
        "cef": {
            "cn1Label": "AuthFactorNo",
            "cn1": 3,
            "cs1Label": "MFAFactorType",
            "cs1": "xxxxx",
            "cn2Label": "VirtualSystemID",
            "cn2": 1,
            "externalId": "xxxxxxxxxxxxx",
            "cs6Label": "MappingDataSourceType",
            "cs6": "netbios_probing",
            "cs5Label": "MappingDataSource",
            "cs5": "probing",
            "dpt": "49760",
            "cn3": 3531,
            "cnt": 1,
            "cat": "0",
            "cs4Label": "MappingDataSourceName",
            "cs4": "fake-data-source-169",
            "cs3Label": "VirtualLocation",
            "cs3": "vsys1",
            "rt": "Mar 01 2021 21:06:02",
            "Name": "logout"
        },
        "related": {
            "user": [
                "xxxxx"
            ],
            "hosts": [
                "paloaltonetwork"
            ],
            "ip": [
                "1.1.1.1"
            ]
        }
    }
    	
	```





## Extracted Fields

The following table lists the fields that are extracted, normalized under the ECS format, analyzed and indexed by the parser. It should be noted that infered fields are not listed.

| Name | Type | Description                |
| ---- | ---- | ---------------------------|
|`@timestamp` | `date` | Date/time when the event originated. |
|`destination.domain` | `keyword` | The domain name of the destination. |
|`destination.ip` | `ip` | IP address of the destination. |
|`destination.mac` | `keyword` | MAC address of the destination. |
|`destination.nat.ip` | `ip` | Destination NAT ip |
|`destination.nat.port` | `long` | Destination NAT Port |
|`destination.port` | `long` | Port of the destination. |
|`destination.user.id` | `keyword` | Unique identifier of the user. |
|`destination.user.name` | `keyword` | Short name or login of the user. |
|`event.action` | `keyword` | The action captured by the event. |
|`event.end` | `date` | event.end contains the date when the event ended or when the activity was last observed. |
|`event.outcome` | `keyword` | The outcome of the event. The lowest level categorization field in the hierarchy. |
|`event.reason` | `keyword` | Reason why this event happened, according to the source |
|`event.severity` | `long` | Numeric severity of the event. |
|`event.start` | `date` | event.start contains the date when the event started or when the activity was first observed. |
|`event.timezone` | `keyword` | Event time zone. |
|`file.inode` | `keyword` | Inode representing the file in the filesystem. |
|`file.mtime` | `date` | Last time the file content was modified. |
|`file.name` | `keyword` | Name of the file including the extension, without the directory. |
|`file.path` | `keyword` | Full path to the file, including the file name. |
|`file.size` | `long` | File size in bytes. |
|`file.type` | `keyword` | File type (file, dir, or symlink). |
|`host.domain` | `keyword` | Name of the directory the group is a member of. |
|`host.hostname` | `keyword` | Hostname of the host. |
|`host.id` | `keyword` | Unique host id. |
|`host.name` | `keyword` | Name of the host. |
|`host.network.egress.bytes` | `long` | The number of bytes sent on all network interfaces. |
|`host.network.ingress.bytes` | `long` | The number of bytes received on all network interfaces. |
|`http.request.method` | `keyword` | HTTP request method. |
|`http.request.referrer` | `keyword` | Referrer for this HTTP request. |
|`log.syslog.facility.name` | `keyword` | Syslog text-based facility of the event. |
|`network.protocol` | `keyword` | Application protocol name. |
|`observer.egress.interface.name` | `keyword` | Interface name |
|`observer.ingress.interface.name` | `keyword` | Interface name |
|`observer.type` | `keyword` | The type of the observer the data is coming from. |
|`observer.vendor` | `keyword` | Vendor name of the observer. |
|`observer.version` | `keyword` | Observer version. |
|`process.name` | `keyword` | Process name. |
|`rule.id` | `keyword` | Rule ID |
|`server.ip` | `ip` | IP address of the server. |
|`server.nat.ip` | `ip` | Server NAT ip |
|`service.name` | `keyword` | Name of the service. |
|`source.domain` | `keyword` | The domain name of the source. |
|`source.ip` | `ip` | IP address of the source. |
|`source.mac` | `keyword` | MAC address of the source. |
|`source.nat.ip` | `ip` | Source NAT ip |
|`source.nat.port` | `long` | Source NAT port |
|`source.port` | `long` | Port of the source. |
|`source.user.name` | `keyword` | Short name or login of the user. |
|`url.original` | `wildcard` | Unmodified original url as seen in the event source. |
|`user_agent.original` | `keyword` | Unparsed user_agent string. |

