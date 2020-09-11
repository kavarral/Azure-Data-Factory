## Using Event Grid to load files into Azure Data Factory

A data factory pipeline is triggered when an event a blob is created in Azure Storage. This example uses Azure Storage Gen2 (without hierarchical namespaces enabled)


1.) Create the container and folder path in Azure Storage where you would like to create the files. This example uses a container called inbound and a folder called jobs.
2.) Create a new trigger and set the container and folder path.  This sample will only pick up files ending with .parquet as depicted in the Blob Path Ends with criteria
3.) When using Event Grid with Azure Data Factory,  you can only trigger on two events: namely Blob Created and Blob Deleted.  This sample is using Blob Created



