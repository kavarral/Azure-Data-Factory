 ## Scale Synapse using the Rest API using Managed Identity
 
 {
    "name": "Scale Synapse",
    "properties": {
        "activities": [
            {
                "name": "Scale Synapse",
                "type": "WebActivity",
                "dependsOn": [],
                "policy": {
                    "timeout": "7.00:00:00",
                    "retry": 0,
                    "retryIntervalInSeconds": 30,
                    "secureOutput": false,
                    "secureInput": false
                },
                "userProperties": [],
                "typeProperties": {
                    "url": "https://management.azure.com/subscriptions/<add your subscription ID>/resourceGroups/<add your resource group>/providers/Microsoft.Sql/servers/<add your server>/databases/<add your database>?api-version=2014-04-01-preview",
                    "method": "PATCH",
                    "headers": {
                        "Content-type": "application/json"
                    },
                    "body": {
                        "properties": {
                            "requestedServiceObjectiveName": "DW100c"
                        }
                    },
                    "authentication": {
                        "type": "MSI",
                        "resource": "https://management.azure.com/"
                    }
                }
            }
        ],
        "annotations": [],
        "lastPublishTime": "2020-08-25T12:46:28Z"
    },
    "type": "Microsoft.DataFactory/factories/pipelines"
}

