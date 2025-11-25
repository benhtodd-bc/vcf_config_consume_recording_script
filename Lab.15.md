# Lab 15 Creating a Namespace

Objective and Tasks
Create a project in the learning_org portal:

1. Access the Learning Organization Portal

2. Create a Namespace

## Task 1: Access the Learning Organization Portal
You log in to the VCF Automation Learning Organization Portal.
CAUTION
You change Organization to Learning_org instead of System.


1. Launch VCF Automation in a new browser tab.

a. On the Google Chrome bookmarks bar, right-click ```VCF Automation``` and select ```Open``` in new incognito window.

b. If the Your connection is not private message appears, click Advanced and click Proceed to ```sa-vaa01.vcf.sddc.local(unsafe)```

* Under Organization name, enter ```learning_org```

c. Log in to the VCF Automation portal.

* **User name:** ```student1```

* **Password:** ```VMware123!VMware123!```

2. Leave the portal open for the next task.

## Task 2: Create a Namespace
You create a namespace using a default namespace class and default VPC for the default project.

1. Click ```Projects``` under the ```Manage & Govern``` tab.

2. Click ```learning-project```.
The ```Learning-project``` page appears.

3. Click the ```Namespaces``` tab.

4. Create a namespace.

    a. Click ```+ NEW NAMESPACE```
    The New Namespace window appears.

    b. In the ```Name``` text box, enter ```learning-project-ns1```

    c. In the ```Namespace``` class field, select ```small```.
    ```Place your cursor in the text box for the options to appear```.

    d. Under ```Region```, select ```region1```.

5. In the VPC field, select ```learning-vpc```.
learning-vpc was created in the previous lab.

6. In the ```Zones``` field, select the ```vspherezone-1``` checkbox.

7. Turn on the ```Override pre-defined``` resource limits ```toggle to enable it```.

    a. Enter the values from the table.

    |Topic |Action|
    |---|---|
    |Memory limit |128 GB|
    |Memory reservation |Leave blank.|
    |CPU limit |10 GHZ|
    |CPU reservation |Leave blank|
    |supervisor-storage-policy |100 GB|
    |||

8. Click ```CREATE```

9. Verify that the new namespace is created.

10. Close the Chrome browser.