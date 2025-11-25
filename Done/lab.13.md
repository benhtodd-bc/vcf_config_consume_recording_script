# Lab 13 Creating a VPC

Objective and Tasks
Create a Virtual Private Cloud for deploying workloads in the Learning_Org organization:

1. Access the Learning Organization Portal

2. Create a VPC

## Task 1: Access the Learning Organization Portal
You log in to the VCF Automation Learning Organization Portal.

||
|:--|
|CAUTION|
|You change Organization to Learning_org instead of System.|
|
1. Launch VCF Automation in a new browser tab.

    a. On the Google Chrome bookmarks bar, right-click VCF Automation and select Open in new incognito window.

    b. If the Your connection is not private message appears, click Advanced and click Proceed to sa-vaa01.vcf.sddc.local(unsafe).

    * Under Organization name, enter learning_org

    c. Log in to the VCF Automation portal.

    * **User name:** ```student1```

    * **Password:** ```VMware123!VMware123!```

2. Leave the portal open for the next task.

## Task 2: Create a VPC
You create a VPC in Learning_Org.

1. Click ```Organizations``` under ```Infrastructure```.

2. Click ```Learning_Org```.

3. On the ```Learning_Org``` page, click ```LAUNCH ORGANIZATION PORTAL```

    ```The Learning_Org organization portal is launched.```

4. Click the ```Manage & Govern``` tab.

    a. Click ```Virtual Private Clouds``` under ```Networking```.

5. Click ```+ NEW VPC``` to create a VPC.

6. Enter the values in the Create VPC wizard.

|||
|:--|:--|
|Name| ```learning-vpc```|
|Description |Leave blank.|
|Region |Select ```region1```|
|Connectivity profile |Verify that ```default@region1``` is selected.|
|'Private-VPC' IPv4 CIDRs |```192.168.100.0/24```|
|IP quotas |Leave the default value.|
|||

7. Click ```CREATE```.

8. Verify that the new VPC is created successfully.

||
|:--|
|IMPORTANT|
|This VPC will be used to deploy workloads in a future lab.|
||

9. Close the Chrome browser window.