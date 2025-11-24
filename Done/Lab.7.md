# Lab 7 Deploying a VM with the VM Service

## Objective and Tasks

Use the VM Service to deploy a VM:

1. Create a Content Library
2. Upload a VM Template to the Content Library
3. Add the Content Library to the vSphere Namespace
4. Deploy a VM

### Task 1: Create a Content Library

You create a content library for storing VM Service templates.

1. Log in to the vSphere Client.
   
   a. In Google Chrome, click ```Workload Domain > vSphere Client (sa-wld01-vc01)``` on the bookmarks bar to open the vSphere Client.
   
   b. Log in the vSphere Client.
   
   * **User name:** ```administrator@vsphere.local```
   
   * **Password:** ```VMware1!```

2. In the vSphere Client, select ```Content Libraries``` from the main menu in the top-left corner.

3. Click ```CREATE```.
   The New Content Library wizard opens.

4. On the Name and location page, enter ```cl_vm``` in the Name text box and click NEXT.

5. On the Configure content library page, verify that Local content library is selected and click ```NEXT```.

6. On the ```Apply security policy``` page, leave the options **UNCHANGED** and click ```NEXT```.

7. On the ```Add storage``` page, select ```sa-wld01-cl01-vsan01``` and click ```NEXT```.

8. Review the configuration and click ```FINISH```.

### Task 2: Upload a VM Template to the Content Library

You upload a template image to the content library.

1. On the ```Content Libraries``` page, click ```cl_vm```.

2. Next to ```cl_vm``` at the top of the page, click ```ACTIONS```.

3. From the drop-down menu, select ```Import item```.

4. Next to Source file, click ```Local File```.

5. Click ```UPLOAD FILES```.

6. Select ```Downloads``` in the navigation pane on the left.

7. Select ```ubuntu-24.04-server.ova``` in the right pane and click Open.

8. Click ``IMPORT``.

   ```NOTE:```This process takes several minutes. It must finish before you can continue. You can
   monitor its progress in the Recent Tasks pane in the vSphere Client.

### Task 3: Add the Content Library to the Namespace

You add the content library to the VM Service on the Namespace.

1. In the vSphere Client, select Supervisor Management from the main menu in the top-left
   corner.

2. Click the Namespaces tab and select namespace-01 in the left navigation pane.

3. Click the Summary tab.

4. In the VM Service pane, click ADD CONTENT LIBRARY.

5. In the Add Content Library dialog box, select the cl_vm and Kubernetes Service
   Content Library checkbox and click OK.
   The VM Service pane now appears above Associated Content Libraries.

6. Click the Terminal icon from the taskbar to open the command line.

7. In Terminal, validate that the virtual machine image is available in the vSphere
   Namespace.

   a. List the VCF contexts.

   ```vcf context list```

   b. Switch to the Supervisor context.

   ```vcf context use context01```

   c. List the virtual machine images in the namespace.

   ```kubectl get virtualmachineImages -n namespace-01 | grep ubuntu-2204-amd64-v1.31.7```

   d. Record the vmi ID of the Ubuntu 22.04 virtual machine image to be used in the next lab task to update the ubuntu VM deployment YAML file. 

   e. List the VM classes that are available in the namespace.

   ```kubectl get virtualmachineclass -n namespace-01```

   The VM class 'best-effort-large' appears in the command output.

   f. List the storage classes that are available in the namespace.

   ```kubectl get storageclass -n namespace-01 | grep supervisor-storage-policy```

### Task 4: Deploy a VM

You use the VM Service to deploy a VM.

1. View the `cloudinit-config` file to review the configMap configuration for use with the VM deployment.

   `cat /home/student01/Downloads/YAML-files/cloudinit-config.yaml`

2. Identify the VMI ID of the `ubuntu-2204-amd64-v1.31.7` image that will be used for deploying a VM.

   `kubectl get virtualmachineImages -n namespace-01 | grep ubuntu-2204-amd64-v1.31.7`

   Copy the VMI ID of the image in a clipboard.

3. Update the ubuntu-vm.yaml file with the VMI ID.

   `sudo vi /home/student01/Downloads/YAML-files/ubuntu-vm.yaml`

   - At the `[sudo] password for student01:` prompt, enter `VMware1!`
   - Press `i` in the VI editor for the INSERT mode.
   - Use the arrow keys to move the cursor to the `imageName`: row.
   - At the imageName: "" row, enter the `VMI ID` within the quotes.
   - Press the `ESC` key to exit from the INSERT mode.
   - Press `:wq` to write and quit the file.

4. Verify the `ubuntu-vm.yaml` manifest file.

   `cat /home/student01/Downloads/YAML-files/ubuntu-vm.yaml`

   The `VirtualMachine` resource includes the parameters in the table.

    <table>
        <thead>
            <tr>
                <th>Parameter </th>
                <th>Value</th>
            </tr>
    </thead>
    <tbody>
    <tr>
    <td>metadata.name</td>
    <td>ubuntu-vm</td>
    </tr>
    <tr>
    <td>spec.imageName</td>
    <td>Ex: vmi-96bb0d25d6f9e57e2<br><br>The VMI ID of an image will be different in your lab.</td>
    </tr>
    <tr>
    <td>StorageClass</td> 
    <td>supervisor-storage-policy</td>
    </tr>
    <tr>
    <td>spec.networkInterfaces.networkName</td>
    <td>sa-m01-vc01-supervisor-wld</td>
    </tr>
    <tr>
    <td>transport</td>
    <td>CloudInit</td>
    </tbody>
    </table>

5. Apply the cloudinit configuration.

    ```kubectl apply -f /home/student01/Downloads/YAML-files/cloudinit-config.yaml```

   configmap/ubuntu-config created message appears. 

6. Deploy the VM.

    ```kubectl apply -f /home/student01/Downloads/YAML-files/ubuntu-vm.yaml```

    The ```virtualmachine.vmoperator.vmware.com/ubuntu-vm created``` message appears. 
    
7. Review the status of the ubuntu-vm VM.

    ```kubectl get virtualmachine ubuntu-vm -n namespace-01 -o wide```

    You must wait 5 to 6 minutes, for the ```POWER-STATE``` to change to ```poweredOn``` and for the ```PRIMARY-IP``` column to be populated before you continue. 
    
8. Record the ```PRIMARY-IP``` value of the ```ubuntu-vm``` VM

    
---
### NOTE
---
The ```PRIMARY-IP``` value for the ubuntu-vm VM takes one or two minutes to populate. If the value does not appear, you must run the previous command again to see it.
---

9. Examine the VM created in vSphere.
        
    *a*. Click ```Google Chrome``` from the taskbar.
        
    *b*. In the vSphere UI, select ```Inventory``` from the main menu in the top-left corner.

    *c*. In the navigation pane on the left, expand ```sa-wld.vc01.vcf.sddc.local > sa-wld01-DC > sa-wld01-cl01 > Namespaces > namespace-01```
        
    The ubuntu-vm VM is listed. The VM controls are disabled because the VM is deployed by the VM service and can only be managed using kubectl.
