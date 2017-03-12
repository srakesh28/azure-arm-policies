# azure-arm-policies
#Sample ARM Policies for Subscription and Resource Groups


How to Apply Tags on RG with Policies

Step1) Create a file called append-notags.json with below format, this will Add Tags to all resources in RG 

<see append-notags.json file>



Step2) Create a Policy 

sudo az policy definition create --name tagPolicyDefinition --description "Policy to Append tags to Resources in RG" --rules append-notags.json

Step3) Assign a Policy to RG within a Subscription

sudo az policy assignment create --name tagPolicyAssignment --policy tagPolicyDefinition --scope /subscriptions/<subscription id>/resourceGroups/<resource group>

Step4) Display Policy in Effect

sudo az policy definition show --name tagPolicyDefinition

Step5) Delete Policy if not required 

sudo az policy assignment delete --name tagPolicyAssignment --scope /subscriptions/<subscription id>/resourceGroups/<resource group>

