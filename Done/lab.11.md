# Lab 11 Configuring Provider
Networking

Objective and Tasks
Set up provider networking:
1. (Optional) Log In to the VCF Automation Provider Management Portal
2. Verify Edge Cluster Import
3. Create an IP Space
4. Create a Provider Gateway
5. Set Up Organization Networking

## Task 1: (Optional) Log In to the VCF Automation Provider
Management Portal
In this lab, you log in to the VCF Automation Provider Management Portal as the local admin.

1. On the Google Chrome bookmarks bar, right-click VCF Automation and select Open in
new incognito window.

a. If the Your connection is not private message appears, click Advanced
and click Proceed to ```sa-vaa01.vcf.sddc.local(unsafe)```.

i. Under ```Organization``` name, enter ```system```

b. Log in to the VCF Automation Provider Management Portal.

* From the first drop-down menu, select ```Log in with local account```.

* **User name:** ```admin```

* **Password:** ```VMware123!VMware123!```

c. Leave the VCF Automation Provider Management Portal open for the next task.

## Task 2: Verify Edge Cluster Import
You verify that the edge cluster has been successfully imported.

1. Click ```Networking``` under ```Infrastructure```.

2. On the ```Networking``` page, click ```Edge Clusters```.

3. Click ```SYNC```.

4. Verify that the ```sa-wld01-cl01``` edge cluster is available.

## Task 3: Create an IP Space
You create an IP space.

1. Click ```Networking``` under ```Infrastructure```.

2. Click the ```IP Spaces``` tab.

3. Click ```NEW```.

    The Create IP Space wizard appears.

4. Specify details for ```Configure General``` Settings.

    a. In the ```Name text box```, enter ```region1_IP_Space```

    b. From the ```region``` drop-down menu, select ```region1```.

    c. Click ```NEXT```.

5. Specify the IP Block and External Reachability.

    a. In the ```IP Block text box```, enter ```10.10.10.32/27```

    * Click ```+ ADD``` to add the IP range.

    b. Click ```NEXT```.

6. Specify Default Quota Settings values.

    a. For Number of Single IPs, select the Unlimited checkbox.

    b. For Number of CIDRs, select the Unlimited checkbox.

    c. For ```Maximum Subnet Size```, select the No Restriction checkbox.

    d. Click ```NEXT```.

7. Verify the settings in the ```Review and Complete``` pane.

    a. Click ```CREATE```

8. Verify that the IP space is created.

## Task 4: Create a Provider Gateway
You create a provider gateway.

1. Click ```Networking``` under ```Infrastructure```.

2. Click the ```Provider Gateways``` tab.

3. Click ```NEW``` to create a ```provider gateway```.

4. Specify details for ```Configure General Settings```.

    a. In the Name text box, enter region1_pg

    b. From the Region drop-down menu, select region1.

    * Click NEXT.

5. Under ```Select T0 Gateway```, select the ```sa-wld01-t0-01``` checkbox.

    a. Click ```NEXT```.

6. Under ```Associated IP Spaces```, select the r```egion1_IP_Space``` checkbox.

    a. Click ```NEXT```.

7. Verify the settings in the ```Review and Complete``` pane 
    * click ```CREATE```.

8. Verify that ```region1_pg``` is created successfully.

## Task 5: Set Up Organization Networking
You set up regional networking for the ```Learning_org``` organization.

1. Click ```Organizations``` under ```Infrastructure```.

2. Click ```Learning_Org```.
The Learning_Org page appears.

3. Select ```Networking```.

4. Click ```EDIT``` to edit the log name.

    a. In the ```Log Name``` text box, enter ```learning```

    b. Click ```SAVE```.

5. Under ```Regional Networking```, click ```NEW```.

6. From the ```Select Region``` drop-down menu, select ```region1```.

    a. Click ```NEXT```.

7. Under ```Select Provider Gateway```, select the ```region1_pg``` checkbox.

    a. Click ```NEXT```.

8. Specify the details for the Select Edge Cluster section.

    a. Select ```Select a specific Edge Cluster```.

    b. Select ```sa-wld01-cl01.```

    c. Click ```NEXT```.

9. In the Review and Complete section, click CREATE.