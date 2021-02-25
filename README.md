# Bank Marketing Classification

This dataset contains data from a direct marketing campaign through phone calls of a Portuguese banking institution. The classification goal is to predict if a client will subscribe to one of the bank's product: bank term deposit, represented by the variable, y.

This model is then deployed as a REST endpoint so that others can query it and get a prediction. For Debugging and Monitoring purposes the logging was enabled.

[Bank Marketing Dataset](https://automlsamplenotebookdata.blob.core.windows.net/automl-sample-notebook-data/bankmarketing_train.csv)

For more details of the dataset visit [Bank Marketing](https://archive.ics.uci.edu/ml/datasets/bank+marketing)

## Architectural Diagram

![Archihtecture](./images/architecture.png)

# Key Steps
## Service Principal
Service Principal is created using Azure Cli as shown below using the azure cli commands provided in the lessons
![Service Principal](./images/service-principal.png)

## Dataset
Dataset provided in the project is uploaded to the azure blobs of workspace datastore. 
![Dataset](./images/dataset.png)

## AutoML Experiment
An AutoML experiment is created and run for the dataset, as shown below
![AutoML Experiment](./images/exp-complete.png)

## Best Model
AutoML executed multiple models and varius types of algorithms we can se the metrics as below
![Best Model](./images/best-model.png)

## Deployment
Best model which is the outcome of the AutoML runs is deployed as show below
![Deployed Model](./images/deeployed-model.png)

## Logging
We choose the best model for deployment and enable "Authentication" while deploying the model using Azure Container Instance (ACI). The executed code in logs.py enables Application Insights. "Application Insights enabled" is disabled before executing logs.py.
![Enable Logging](./images/logs.png)

## Enable AppInsights
AppInsights are enabled using the log.py script
![Enabled AppInsights](./images/app_insights.png)


## SwaggerUI
Swagger is used to get the documentation of the api as below for get and post  methods.
![SwaggerUI](./images/swagger-1.png)
![SwaggerUI](./images/swagger-2.png)
![SwaggerUI](./images/swagger-3.png)

## Consuming
we can test the deployed endpoint using the endpoint.py script which has sample input payloads
![Consuming](./images/consuming.png)

## Pipeline Deploy

Deploying Pipeline as endpoints is a methods to deploy pipelines that can be called by a rest endpoint which runs on scalable compute clusters instead of ACI/AKS for Real time endpoinds.

We can see deployed automl pipeline as an endpoint with active status
![Pipeline Deploy](./images/pipeline-deploy.png)

Pipelines endpoints tab in endpoints provides us the details of all the pipeline endpoints that are deployed. Here is the pipeline endpoint we deployed
![Pipeline Deploy](./images/pipelines-list.png)

## Pipeline Endpoint
deployed Pipeline endpoint
![Pipeline Endpoint](./images/pipeline-endpoint.png)

## Pipeline Run
Below is the example of the pipeline run that is invoked by calling the pipeline rest endpoint that was deployed in previous steps
![Pipeline Run](./images/pipeline1.png)

![Pipeline Run](./images/run.png)


## Screen Recording


[Link to Screencast Recording](https://youtu.be/J067tN5ZBzU)


## Standout Suggestions
### Improving the project

Some ways to improve this project are:

 - Data has lot of imablance in the classes. Aaccuray is not the right metric to use in this scenario and we can make efforts to handle imbalance in the classes
 - Efficient handling of outliers can lead to further improvement of the model
 - Applying feature selection techniques might improve the model
