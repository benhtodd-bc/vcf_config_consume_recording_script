Here is the full markdown version of Lab 5, "Creating and Configuring a vSphere Namespace," from the document, with inputs and values formatted in code blocks.

## Lab 5 Creating and Configuring a vSphere Namespace 

### Objective and Tasks 

Create and configure a vSphere Namespace: 

1.  Create vSphere Namespace 
2.  Configure vSphere Namespace 

### Task 1: Create vSphere Namespace 

You create a vSphere Namespace in the vSphere Client. 

1.  Log in to the vSphere Client. 
2.  a. On the Ubuntu taskbar, click the **Google Chrome** icon. 
    b. Click **Workload Domain folder \> vSphere Client (sa-wld01-vc01)** on the bookmarks bar to open the vSphere Client. 
    c. Log in to the vSphere Client. 
      * User name:
        ``` 
        administrator@vsphere.local
        
        ```
        
      * Password:
        ``` 
        VMware123!VMware123!
        
        ```
        
        (Optional) In the vSphere Client, select **Supervisor Management** from the main menu in the top-left corner. 
3.  Click
    ``` 
    supervisor01
    
    ```
    . 
4.  On the **Supervisor Management** page, click the **Namespaces** tab. 
5.  Click **NEW NAMESPACE**. 
    The **Create Namespace** wizard opens. 
    a. On the **Location** page, select
    ``` 
    supervisor01
    
    ```
    . 
    b. Click **NEXT**. 
    c. On the **Configuration** page, enter
    ``` 
    namespace-01
    
    ```
    in the **Name** text box. 
    d. Click **NEXT**. 
    e. On the **Add Zones** page, verify that
    ``` 
    vspherezone01
    
    ```
    is selected. 
    f. Click **NEXT**. 
    g. On the **Review** page, click **FINISH**. 
6.  On the *Your namespace namespace-01 has been successfully created* message, click **GOT IT**. 

### Task 2: Configure vSphere Namespace 

You configure the new vSphere Namespace to add storage policy and VM class. 

1.  On the **Summary** tab of the
    ``` 
    namespace-01
    
    ```
    page, click **ADD STORAGE** in the **Storage** pane. 
2.  In the **Select Storage Policies** dialog box, select the
    ``` 
    supervisor-storage-policy
    
    ```
    checkbox and click **OK**. 
3.  Add a VM class. 
    a. In the **VM Service** pane, click **ADD VM CLASS**. 
    b. Select the
    ``` 
    best-effort-small
    
    ```
    checkbox and click **OK**. 
    The associated VM classes determine the resource sizing of virtual machines that can be deployed in the namespace. 

**NOTE** 
In a production environment, using a guaranteed VM class is the best practice. 
