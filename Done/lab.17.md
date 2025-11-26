# Lab 17 Creating a Load Balancer

Objective and Tasks
Create a load balancer in learning_org:

1. (Optional) Log In to the VCF Automation Organization Portal

2. Deploy a Load Balancer

3. Test the Connectivity

## Task 1: (Optional) Log In to the VCF Automation Organization
Portal
You log in to the VCF Automation Organization Portal.

1. On the Google Chrome bookmarks bar, right-click VCF Automation and select Open in
new incognito window.

    a. If the Your connection is not private message appears, click Advanced and click Proceed to ```sa-vaa01.vcf.sddc.local(unsafe).```

    b. Under Organization name, enter learning_org

    c. Log in to the VCF Automation Organization Portal.

    * From the first drop-down menu, select Log in with local account.

    * ***User name:*** ```student1```

    * **Password:** ```VMware123!VMware123!```

    d. Leave the VCF Automation Organization Portal open for the next task.

## Task 2: Deploy a Load Balancer

1. Click ```Network``` under ```Services```.

2. Click the ```VM Load Balancers``` tab.

3. Click ```+ CREATE```.

The Create VM Load Balancer window opens.

|Option |Value|
|---|---|
|Name |vm-lb-01|
|Selector |leave the default name|
|Name |ssh|
|Port |22|
|Protocol |TCP|
|Target |22|
|||

a. Click ```ADD```.

4. Click ```CREATE```.

5. Click ```vm-lb-01``` under ```VM Load Balancers```.

6. Verify that the ```vm-lb-01``` is created with an External ```IP 10.10.10.xx```

7. Click ```VIEW YAML``` next to ```vm-lb-01``` to open the YAML file.

||
|---|
|The YAML file appears in the YAML viewer in the same screen. Place the cursor at the edge of the window and drag the border of the window to maximize the view of the YAML editor|
||

8. Click the ```Pencil``` icon to ```edit``` the YAML file.

9. In the ```YAML editor```, at the ```Line No 20```, ```change``` the ```selector``` from ```vm-lb-01``` to ```vm-selector``` and ```vm-lb-selector``` to ```vm-ubuntu```.

a. Click ```SAVE```.

b. Click ```Collapse``` to close the YAML Editor.

c. CLICK ```←``` ```BACK``` to go back to VM Load Balancers.

10. Click the ```Services``` tab to verify the ```Load Balancer cluster IP``` and ```External IP``` assigned to the ```VM Load Balancer```.

## Task 3: Test the Connectivity

1. From the Console desktop, click Terminal from the taskbar to open.

2. Ping the External IP address assigned to the virtual machine


    ```ping -c 4 10.10.10.34```

3. Initiate an ```SSH``` ```session``` to the external IP assigned to the virtual machine.

    ```ssh ubuntu-user@10.10.10.34```

4. At the ```Are you sure you want to continue connecting (yes/no/[fingerprint])?``` prompt, enter ```yes```

5. When prompted for the ```password```, enter ```VMware123!VMware123!```

6. Close the SSH session to 10.10.10.34. ```exit```

7. Click ```X``` to close the Terminal window.