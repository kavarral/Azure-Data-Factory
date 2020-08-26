## Pause Azure Synapse using the Rest API and Managed Identity


"properties": { <br/>
	"activities": [ <br/>
            { <br/>
                "name": "Pause AzureSynapse", <br/>
                "type": "WebActivity", <br/>
                "dependsOn": [], <br/>
                "policy": { <br/>
                    "timeout": "7.00:00:00", <br/>
                    "retry": 0, <br/>
                    "retryIntervalInSeconds": 30, <br/>
                    "secureOutput": false, <br/>
                    "secureInput": false <br/>
                }, <br/>
                "userProperties": [], <br/>
                "typeProperties": { <br/>
                    "url": "https://management.azure.com/subscriptions/&lt;add your subscription ID>/resourceGroups/&lt;add your resource group>/providers/Microsoft.Sql/servers/&lt;add your server>/databases/&lt;add your database>/pause?api-version=2017-10-01-preview", <br/>
                    "method": "POST", <br/>
                    "authentication": { <br/>
                        "type": "MSI", <br/>
                        "resource": "https://management.azure.com/" <br/>
                    } <br/>
                } <br/>
            } <br/>
        ], <br/>
        "annotations": [], <br/>
        "lastPublishTime": "2020-08-25T11:04:13Z" <br/>
    }, <br/>
    "type": "Microsoft.DataFactory/factories/pipelines" <br/>
