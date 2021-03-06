FORMAT: 1A
HOST: https://polls.apiblueprint.org/

# SNOW App Config APIs


### SNOW instance activation API [POST]

+ Request (application/json)

     + URL: /integrations/{integrationCode}/activate
        
     + Headers

            Content-Type: application/json
            
     + Body
            
            {
                "instanceId": "snow.instance.identifier"
            }
        

+ Response 200 (application/json)

    + Headers

            Content-Type: application/json

    + Body

            {
                "status": "success",
                "response": {
                    "integrationId": "ea67aa08-2c3f-4513-bd0f-7fe1cf53dc57",
                    "partnerId": "",
                    "isPartner": false,
                    "customerId": "MSP_029929",
                    "customerName": "Elite Networks",
                    "ciManagement": "CUSTOMER"
                }
            }

### NEP customers list API [GET]

+ Request (application/json)

     + URL: /integrations/{integrationId}/customers
     
     + Headers

            Content-Type: application/json
            
     + Body
            
            N/A
        

+ Response 200 (application/json)

    + Headers

            Content-Type: application/json

    + Body

            {
              "status": "success",
              "response": [
                {
                  "customerId": "CY_92XY_0932",
                  "customerName": "ClientX"
                },
                {
                  "customerId": "CY_92AB_0862",
                  "customerName": "ClientY"
                }
              ]
            }
            
### NEP entities list API [GET]

+ Request (application/json)

     + URL: /integrations/{integrationId}/entities
     
     + Headers

            Content-Type: application/json
            
     + Body
            
            N/A
        

+ Response 200 (application/json)

    + Headers

            Content-Type: application/json

    + Body

            {
              "status": "success",
              "response": [
                {
                  "name": "asset",
                  "description": "NE Platoform normalized asset model",
                  "source": "NEP",
                  "version": "v1.0",
                  "attributes": null
                },
                {
                  "name": "incident",
                  "description": "NE Platoform normalized incident model",
                  "source": "NEP",
                  "version": "v1.0",
                  "attributes": null
                }
              ]
            }
            
### SNOW-NEP customer mapping API [POST]

+ Request (application/json)

     + URL: /integrations/{integrationId}/customers/mappings
        
     + Headers

            Content-Type: application/json
            
     + Body
            
            {
              "customers": [
                {
                  "customerId": "23883",
                  "externalCustomerId": "23892383"
                }
              ]
            }
        

+ Response 200 (application/json)

    + Headers

            Content-Type: application/json

    + Body

            {
              "status": "success",
              "response": {
                "customers": [
                  {
                    "customerId": "23883",
                    "customerName": null,
                    "externalCustomerId": "23892383"
                  }
                ],
                "integrationId": "22323"
              }
            }
          
### NEP entity model get API [GET]

+ Request (application/json)

     + URL: /integrations/{integrationId}/entities/{entityName}
     
     + Headers

            Content-Type: application/json
            
     + Body
            
            N/A
        

+ Response 200 (application/json)

    + Headers

            Content-Type: application/json

    + Body

            {
                "status": "success",
                "response": {
                    "name": "asset",
                    "description": "NE Platoform normalized asset model",
                    "source": "NEP",
                    "version": "v1.0",
                    "attributes": null
                }
            }
            
            
### SNOW-NEP entity mapping API [POST]

+ Request (application/json)

     + URL: /integrations/{integrationId}/entities/mappings
        
     + Headers

            Content-Type: application/json
            
     + Body
            
            {
                "entityName": "Asset",
                "externalEntityName": "ConfigurationItem",
                "source": "SNOW",
                "attributeMappings": {
                    "assetId": {
                      "key": "ci_id",
                      "name": "Configuration Item Id",
                      "dataType": "string",
                      "required": true
                    },
                    "customerId": {
                      "key": "client_id",
                      "name": "Customer Id",
                      "dataType": "string",
                      "required": true
                    },
                    "partnerId": {
                      "key": "partner_id",
                      "name": "Partner Id",
                      "dataType": "string",
                      "required": false
                    },
                    "priority": {
                      "key": "criticality",
                      "name": "Criticalisty",
                      "dataType": "enum",
                      "required": false,
                      "defaultValue": "P0"
                    }
                }
            }
        

+ Response 200 (application/json)

    + Headers

            Content-Type: application/json

    + Body

            {
              "status": "success",
              "response": "Integration entity mapping created successfully"
            }
            
### NEP entity object get API [GET]

+ Request (application/json)

     + URL: /integrations/{integrationId}/entities/{entityName}/{entityId}
     
     + Headers

            Content-Type: application/json
            
     + Body
            
            N/A
        

+ Response 200 (application/json)

    + Headers

            Content-Type: application/json

    + Body

            {
                "status": "success",
                "response": {
                    "assetSubtype": "windows",
                    "skus": [
                        {
                            "name": "Servers Type 1&Virtual Hypervisor",
                            "description": "Servers Type 1&Virtual Hypervisor",
                            "id": "NE6087"
                        }
                    ],
                    "bios": {
                        "smBiosVersion": "090006",
                        "biosName": "Intel(R) Xeon(R) CPU E5-2623 v3 @ 3.00GHz",
                        "systemManufacturer": "Microsoft Corporation",
                        "smBiosMinorVersion": 3,
                        "smBiosPresent": true,
                        "systemSerial": "6112-8548-3244-9207-8098-9468-83",
                        "biosVersion": "090006",
                        "systemModel": "Virtual Machine",
                        "smBiosMajorVersion": 2
                    },
                    "partnerName": null,
                    "recordCreatedTime": null,
                    "servicePackage": "N - EES MANAGE",
                    "source": [
                        {
                            "agentVersion": "7.0.4",
                            "sourceAssetId": "6feaf1ef-e83a-4b80-833f-1e6736d3161e",
                            "name": "Opsramp",
                            "sourceCreatedTime": 1599816277000,
                            "type": "CMDB",
                            "clientId": "client_712554"
                        }
                    ],
                    "assetId": "C_65_1824968040__device__pmi_file_01",
                    "customAttributes": null,
                    "partnerId": "P-65-2223207256",
                    "assetName": "PMI-FILE-01",
                    "assetType": "device",
                    "consoles": [
                        {
                            "consoleAuthType": "PASSWORD",
                            "port": 3389,
                            "consoleConnector": "Agent",
                            "ipAddress": "127.0.0.1",
                            "type": "MANAGEMENTCONSOLE",
                            "consoleProtocol": "RDP"
                        }
                    ],
                    "recordUpdatedTime": 1600198143688,
                    "discoveryContext": [
                        {
                            "assetName": "PMI-FILE-01",
                            "assetType": "DEVICE",
                            "index": 0
                        }
                    ],
                    "managementProfile": {
                        "name": "PMI-OpSram-gw",
                        "description": null,
                        "id": 56634,
                        "type": "Gateway"
                    },
                    "ipAddress": [
                        "192.168.192.11"
                    ],
                    "assetStatus": "UP",
                    "tags": null,
                    "serviceProviderId": "EPICID-57-3201882173",
                    "assetState": "active",
                    "location": {
                        "address": "3150 SCOTT DR",
                        "city": "COLUMBUS",
                        "name": "PRECISE TOOLING SOLUTIONS INC_30141280",
                        "mspId": "56",
                        "description": "30141280",
                        "id": 965469,
                        "clientId": "712554"
                    },
                    "customerName": "PRECISE TOOLING SOLUTIONS INC",
                    "customerId": "C-65-1824968040",
                    "device": {
                        "assetApps": [
                            {
                                "appVendor": null,
                                "appName": "Ubiquiti UniFi (remove only)",
                                "appVersion": "",
                                "appModifiedDate": 1600182000000,
                                "appCreatedDate": 1599816277000,
                                "appInstalledDate": null,
                                "appId": "2218664869"
                            }
                        ],
                        "deviceType": "windows",
                        "checkType": null,
                        "generalInfoDns": [
                            "PMI-FILE-01.PreciseMold.local"
                        ],
                        "physicalMemory": "7.81",
                        "antivirusDetailsStatus": null,
                        "hostname": "PMI-FILE-01",
                        "generalInfoMacAddress": [
                            "00:15:5D:C0:17:00"
                        ],
                        "antivirusDetailsLastScannedTime": 1600117206000,
                        "publicIpAddresses": null,
                        "resourcePath": "Server >> Windows",
                        "host": null,
                        "generalInfoCreatedTime": 1599816277000,
                        "generalInfoUpdatedTime": 1600182000000,
                        "totalApps": 31,
                        "org": null,
                        "publicIpFlag": false,
                        "firstAssetManagedTime": 1599816277000,
                        "privateIpAddresses": null,
                        "aliasName": null,
                        "uri": null,
                        "encodingType": "UTF8",
                        "osType": "Microsoft",
                        "name": "PMI-FILE-01",
                        "keyboardType": "US104",
                        "osName": "Microsoft Windows Server 2012 R2 Standard",
                        "antivirusDetailsVendor": null,
                        "category": "windows",
                        "asn": null,
                        "classCode": "virtuvalmachine"
                    }
                }
            }
        
