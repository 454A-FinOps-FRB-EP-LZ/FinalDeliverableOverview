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
