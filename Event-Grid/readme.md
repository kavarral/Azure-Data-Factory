## Using Event Grid to load files into Azure Data Factory

```
! NOTE 
The Event Trigger currently supports only Azure Data Lake Storage Gen2 and General-purpose version 2 storage accounts. 
You must have at least Owner access on the storage account. 
Due to an Azure Event Grid limitation, Azure Data Factory only supports a maximum of 500 event triggers per storage 
account.
```

A data factory pipeline is triggered when an event a blob is created in Azure Storage. This example uses Azure Storage Gen2 (without hierarchical namespaces enabled)

1.) Create the container and folder path in your Azure Storage where you would like to drop or create the files. This example uses a container called inbound and a folder called jobs.

2.) Create a new trigger and set the container and folder path. This sample will only pick up files ending with .parquet as depicted in the Blob Path Ends with criteria

3.) When using Event Grid with Azure Data Factory,  you can only trigger on two events: namely Blob Created and Blob Deleted.  This sample will trigger when a blob file is created

You can refer to this document for more detail

[Event Grid with Azure Data Factory](https://docs.microsoft.com/en-us/azure/data-factory/how-to-create-event-trigger)

<img src="https://github.com/kavarral/Images/blob/master/ADFTrigger.PNG?raw=true" />

4.) Create a new ADF pipeline

5.) Add two parameters to the pipeline, one called folderPath and one called fileName 

<img src="https://github.com/kavarral/Images/blob/master/EventGrid_PipelineParameters.PNG?raw=true" />

6.) Create a copy activity. The source will be the same storage account you configured for the Trigger.

7.) Edit the Source Dataset add two parameters one called folderPath and one called fileName.

7.) In the connection File Path, enter the following dynamic values to pass the Folder Path and File Name from the pipeline to the dataset
<img src="https://github.com/kavarral/Images/blob/master/EventGrid_Souce.PNG?raw=true" />

8.) In the source dataset, pass the parameters dynamically to the parameters from the pipeline as follows: 
<img src="https://github.com/kavarral/Images/blob/master/EventGrid_SouceDataset.PNG?raw=true" />

9.) Configure the Sink. 

10.) Add the Trigger to the Pipeline. When you add the trigger you will be prompted to enter a value for the parameters will be passed to the pipeline. Add the following values for the folderPath and fileName parameters

<img src="https://github.com/kavarral/Images/blob/master/TriggerParameters.PNG?raw=true" />

11.) Upload or copy and paste a file into the container and/or folder you specified to test 




