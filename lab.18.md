# Lab 18 Creating a VKS Cluster

## Objective and Tasks

Create a VKS Cluster in learning_org:

1. Create a VKS Cluster
2. Monitor the VKS Deployment in vCenter
3. Verify the VKS Cluster Configuration

### Task 1: Create a VKS Cluster

In this lab you create a VKS Cluster using the Organization portal.
1. In the Organization portal, click the ```Build & Deploy``` tab.

2. Click ```Kubernetes``` under Services.

3. Click ```+ CREATE```.
    
    The ```New Kubernetes``` Cluster wizard opens.

4. On Configuration Type, select ```Custom Configuration``` and click NEXT.

5. Enter ```vks-cluster-1``` in the cluster name text box.

6. Click the ```Kubernetes release``` drop-down menu and verify that ```v1.32.0---vmware.6-fips-vkr.2 is selected```.

7. Scroll down to the end of the ```General Settings``` page and click ```NEXT```.

8. Click the ```Replicas``` drop-down menu and select ```1```.

9. Select ```best-effort-medium``` from the VM Class list.

10. In the ```Storage Class``` drop-down menu, verify that ```supervisor-storage-policy``` is selected.

11. Click ```NEXT``` to proceed to the ```4. Nodepools``` section.

12. Click ```+ ADD NODEPOOL```.

The ```Add Nodepool``` wizard opens.

13. Complete the configuration to add nodepool.
        <table>
        <thead>
        <th>Option</th>
        <th>Value</th>
        </thead>
        <tbody>
        <tr>
        <td>Name</td>
        <td>Leave the default name</td>
        </tr>
        <tr>
        <td>Class</td>
        <td>node-pool</td>
        </tr>
        <tr>
        <td>Zone</td>
        <td>vspherezone01</td>
        </tr>
        <tr>
        <td>Replicas</td>
        <td>3</td>
        </tr>
        <tr>
        <td>VM Class</td>
        <td>best-effort-medium (2 vCPUs and 8Gi RAM)</td>
        </tr>
        <tr>
        <td>Storage Class</td>
        <td>supervisor-storage-policy</td>
        </tr>
        <tr>
        <td>OS image</td>
        <td>Photon 5 - Kubernetes Service Content Library</td>
        </tr>
        </tbody>
        </table>

    a. Click NEXT.
    b. Click FINISH.

14. Click ```NEXT```.

15. Click ```FINISH```.

    You monitor the tasks running in the vSphere Client for creating the VKS cluster.

### Task 2: Monitor the VKS Deployment in vCenter
1. Open a new tab in Google Chrome.
    
    a. From the bookmarks toolbar, select Workload Domain>vSphere Client (sa-wld01-vc01)
    
    b. Log in to the vSphere Client:
        
    * **User name:** ```administrator@vsphere.local```

    * **Password:** ```VMware123!VMware123!```

2. Expand ```sa-wld01-vc01.vcf.sddc.local > sa-wld01-DC > sa-wld01-cl01```.

3. Expand ```Namespaces```.

4. Expand ```learning-project-ns1-XXXXX```.

    **XXXXX is a system-generated alphanumeric value.**

5. Expand ``vks-cluster-1.``

6. Monitor Recenter Tasks to verify the ```vks-cluster-1``` tasks.
The VKS Cluster creation typically takes about 60 to 70 mins for the deployment to
complete.

7. In Google Chrome, click the VCF Automation Organization Portal.

8. Monitor the vks-cluster-1 status.
The node status changes from Not Ready to Provisioned and finally to the Ready status.

### Task 3: Verify the VKS Cluster Configuration
In this lab you verify the vks-cluster-1 configuration.
1. Click vks-cluster-1.
2. Click DOWNLOAD KUBECONFIG FILE.
3. Click Save.
4. Verify the cluster Details from the Summary tab.
Options Value
Status Ready
Kubernetes Release v1.32.0---vmware.6-fips-vkr.2
Certificate Rotation Enabled; 90 Days
CNI Antrea
Pods CIDR 192.168.156.0/20
Services CIDR 10.96.0.0/12
Service Domain cluster.local
Replicas 1 (Control plane), 3 (node-pool)
VM Class best-effort-small
Storage Class supervisor-storage-policy
OS Image Photon

5. Click Network under Services.

68
6. Verify that vks-cluster-1-control-plane-service is assigned an External IP 10.10.10.xx
with ports 6443/TCP.
7. Click vks-cluster-1-control-plane-service to review the Service Details.
Options Value
Name vks-cluster-1-control-plane-service
Type Load Balancer
Cluster IP 10.96.0.55
External IP 10.10.10.xx (ex: 10.10.10.35)
Ports 6443/TCP
VM vks-cluster-1-xxxx-xxxxx