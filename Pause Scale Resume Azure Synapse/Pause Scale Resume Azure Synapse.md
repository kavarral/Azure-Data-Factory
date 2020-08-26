## Pause, Resume and Scale Azure Synapse Pool using Azure Data Factory

You can Pause, Scale and Resume Azure Synapse Analytics using a variaty of methods. This method requires the least amount of effort in my opinion and calls the REST API to Pause, Resume or Scale Azure Synapse Analytics using a simple Web Activity in Azure Data Factory. 

This example uses a Managed Service Identity.
In order for the REST API to execute successfully, the Azure Data Factory Managed Service requires permission.  

To give the Managed Identidy for Azure Data Factory permissions to scale, pause or resume your Azure Synapse instance:

Navigate to the server where your Azure Synapse Analytics Pool is hosted.  
Click on Access Control IAM in the blade
Add Role Assignment 
Select Contributor 
Assign Access to Azure Data Factory
Select the Azure Data Factory Service from the list which will be used to run the pipeline.

Once this is done,  navigate to the JSON files in this folder. 

Modify the URL accordingly to point to your subscription, resource group and database that you wish to execute the API against.
For the scale, remember to modify the number of DW's that you wish to scale up or down to.  

Copy and paste the JSON
Open Azure Data Factory and create a new pipeline.
Give your pipeline a name.
Edit the pipeline code

Replace the following with your JSON code. 

&nbsp;&nbsp;&nbsp;"properties": { <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;"annotations": [] <br>
&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;&nbsp;} <br>
