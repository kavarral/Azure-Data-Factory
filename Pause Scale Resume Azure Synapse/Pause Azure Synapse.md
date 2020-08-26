## Pause Azure Synapse using the Rest API

{
    "name": "Pause Synapse",
    "properties": {
        "activities": [
            {
                "name": "Pause AzureSynapse",
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
                    "url": "https://management.azure.com/subscriptions/<add your subscription ID>/resourceGroups/<add your resource group>/providers/Microsoft.Sql/servers/<add your server>/databases/<add your database>/pause?api-version=2017-10-01-preview",
                    "method": "POST",
                    "authentication": {
                        "type": "MSI",
                        "resource": "https://management.azure.com/"
                    }
                }
            }
        ],
        "annotations": [],
        "lastPublishTime": "2020-08-25T11:04:13Z"
    },
    "type": "Microsoft.DataFactory/factories/pipelines"
}

