# FinalDeliverableOverview

## Overview of Project

### Relevant Repositories:

terraformTest: This has all the code for the terraform setup.

RestAPIs: This has all the code for the two RestAPI routes (CPU, Memory).

WebDriverTesters: This has all the code for the k6 OSS testing tool.

PriceCalculationScript: This was a simple script created to make pricing model calculations easier.

FinOps_Notes_Updates: This has all the notes we took over the semester as well as the proposal and semester plan.

### How to use:

EC2 Cluster:
To launch the AWS EC2 cluster, run `terraform init` and it will set up all the necessary files needed for terraform. Then run `terraform apply` to apply the IaC declarations to the EC2 cluster. Once done with using the cluster, run `terraform destroy` to tear down all the instances.

RestAPIs:
To test the RestAPIs, make sure to first start the AWS EC2 cluster and to get the link that is printed after running `terraform apply`. Then, you can test the two API routes by adding `/stress/cpu` (to create a CPU load) or `/stress/memory` (to create a memory load) to the end of the link copied from the previous step. Finally, if everything has been done correctly, the two API routes should return a JSON object with the following format: `{"status":"XXX stress test started at YYY% load"}`

Grafana k6 OSS:
To use the k6 OSS testing tool, change the text of the `link` variable in line 34 with the link of the AWS EC2 cluster, then choose the API route to test by changing the text of the `route` variable in line 38 and finally, choose the type of test to perform by changing the text of the `test` variable in line 42. If you want to only perform the tests locally, navigate to the directory where the WebDrivers.js script is located and run `k6 run WebDrivers.js`. However, if you want to perform the tests and also save their results on the cloud, make sure to first configure the k6 OSS testing tool with your Grafana API key and to change the text of the `projectID` field in line 47 inside the ´options´ object with the ID of the project that you want the tests to be binded to. After all of this setup is done, navigate to the directory where the WebDrivers.js script is located and run `k6 cloud WebDrivers.js`.
