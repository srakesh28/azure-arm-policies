# azure-arm-policies
#Sample ARM Policies for Subscription and Resource Groups


<b>How to Apply Tags on RG with Policies</b>

<b> Step1) Create a file called append-notags.json with below format, this will Add Tags to all resources in RG </b>

\<see append-notags.json file>


<b> Step2) Create a Policy </b>

sudo az policy definition create --name tagPolicyDefinition --description "Policy to Append tags to Resources in RG" --rules append-notags.json

<b> Step3) Assign a Policy to RG within a Subscription <\b>

sudo az policy assignment create --name tagPolicyAssignment --policy tagPolicyDefinition --scope /subscriptions/\<subscription id>/resourceGroups/\<resource group>

<b> Step4) Display Policy in Effect </b>

sudo az policy definition show --name tagPolicyDefinition

<b> Step5) Delete Policy if not required  </b>

sudo az policy assignment delete --name tagPolicyAssignment --scope /subscriptions/\<subscription id>/resourceGroups/\<resource group>


