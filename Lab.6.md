# Lab 6 Configuring Permissions on vSphere Supervisor and Namespace

## Objective and Tasks

### Install the command-line tools:
1. Assign Permissions on the Supervisor Cluster
2. Assign Permissions on Namespaces

### Task 1: Assign Permissions on the Supervisor Cluster
You assign permissions on the Supervisor cluster.
1. Log in to the vSphere Client.
    * In Google Chrome, click ```Workload Domain >vSphere Client (sa-wld01-vc01)``` on the bookmarks bar to open the ```vSphere Client```.
    * Log in to the vSphere Client.
        * **User name:** ```administrator@vsphere.local```
        * **Password:** ```VMware123!VMware123!```

2. In the ```vSphere menu```, click ```Supervisor Management```.
3. Click the ```Supervisors``` tab.
4. Click ```supervisor01```.
5. Click the ```Permissions``` tab.
6. Click ```ADD```.
7. On Add Permission, click the ```Domain``` drop-down menu and select ```vclass.local```.
8. In the ```User/Group``` text box, enter ```devops-admin```
9. From the ```Role``` drop-down menu, select ```Supervisor Administrator```.
10. Select the ```Propagate to Children``` checkbox.
11. Click ```OK```.
12. On the ```Permissions``` tab, verify that the ```VCLASS.LOCAL\devops-admin``` user is listed with the ```Supervisor Administrator``` role.

### Task 2: Assign Permissions on Namespaces
You assign permissions on the namespace.
1. Click the ```Namespaces``` tab.
2. Click ```namespace-01```.
3. Click the ```Permissions``` tab.
4. Click ```ADD```.
5. On ```Add Permission```, click the ```Domain``` drop-down menu and select ```vclass.local```.
6. In ```User/Group text box```, enter ```devops-user```
7. From the ```Role``` drop-down menu, select ```Namespaces``` View.
8. Select the ```Propagate to Children``` checkbox.
9. Click ```OK```.
10. On the ```Permissions``` tab, verify that ```VCLASS.LOCAL\devops-user``` is listed with the Namespaces View role.