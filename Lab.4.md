# Lab 4 Downloading and Installing VCF and Kubernetes CLI Tools

## Objective and Tasks
Install the command-line tools:
1. Download the VCF CLI Tool for Linux
2. Install VCF CLI
3. Enable VCF CLI Autocompletion
4. Download the kubectl CLI Tool
5. Install kubectl CLI
6. Enable kubectl CLI Autocompletion
7. Create Context with VCF CLI



You download the VCF CLI Tools for Linux on the student VM. 

1.  On the `supervisor01` page, click **Supervisors** from the navigation pane and go to **Namespaces** tab. 
2.  Open the `svc-tkg-domain-c10` details page. 
    a. On the **Supervisor Management** page, click the **Namespaces** tab. 
    b. Click `svc-tkg-domain-c10`. 
3.  Click the **Summary** tab. 
4.  In the Status pane, click **Open** under **Link to CLI Tools**.  A new browser tab opens. 
5.  If the *Your connection is not private* message appears, click **Advanced** and click **Proceed to 10.10.10.22 (unsafe)**.  The browser redirects to the VCF Consumption Command Line Interface download page. 
6.  Click **DOWNLOAD VCF CLI FOR LINUX (AMD64)**.  The `vcf-cli.tar.gz` file is saved in the `Downloads` directory in the student VM. 

## Task 2: Install VCF CLI 

You install VCF CLI Tools for Linux on the student VM. 

1.  On the Ubuntu taskbar, click the **Terminal** icon. 
2.  Navigate to the `Downloads` directory. 
    
    ``` 
    cd Downloads
    ``` 
    
3.  Unzip the `vcf-cli.tar.gz` file. 
    ``` 
    tar xvf vcf-cli.tar.gz
    ```
    
    
4.  Move VCF CLI Tools to the bin directory. 
    ``` 
    sudo mv vcf-cli-linux amd64 /usr/local/bin/vcf
    ``` 
    a. Enter `VMwarel!` when a prompt appears for the password for `student01`. 
    
    
5.  Display the `vcf` CLI version to ensure that the installation was successful. 
    ``` 
    vcf version
    ``` 
    The output displays the client version, which is based on the version of VMware Cloud Foundation or VMware vSphere Foundation. [cite: 3, page 29]
    
    

## Task 3: Enable VCF CLI Autocompletion 

You enable `vcf` CLI autocompletion to make VCF easier to work with. 

1.  Insert the `vcf` CLI autocompletion data into the `.bash_profile` files. 
    ``` 
    echo 'source <(vcf completion bash)' >> ~/.bash_profile
    ``` 
    Autocompletion is enabled when you open a new terminal. 
    
    
2.  Reload the bash profile. 
    ``` 
    source ~/.bash_profile
    ``` 
    
    
3.  Enter `vcf` followed by a space and then press **Tab** twice.  Autocompletion displays the available `vcf` options. 
    > **NOTE**
    > In later labs, you can press **Tab** twice to autocomplete the commands. 
4.  List the VCF version. 
    ``` 
    vcf version
    ``` 
    
    

## Task 4: Download the kubectl CLI Tool 

You download the `kubectl` CLI binary to the student VM (using `curl`) and verify/prepare its permissions so it's ready for installation. 

1.  Download the `kubectl` CLI command. 
    ``` 
    curl -LO https://dl.k8s.io/release/v1.33.0/bin/linux/amd64/kubectl
    ``` 
    
    
2.  List the permissions on `kubectl`. 
    ``` 
    ls -l kubectl
    ``` 
    
    
3.  Assign executable permissions on a `kubectl` file. 
    ``` 
    sudo chmod +x kubectl
    ``` 
    a. When prompted, enter `VMwarel!` as a password for `student01`. 
    
    
4.  Verify the permissions on the `kubectl` file. 
    ``` 
    ls -1 kubectl
    ``` 
    

## Task 5: Install kubectl CLI 

You install `kubectl` CLI Tools for Linux on the student VM. 

1.  Move `kubectl` CLI Tools to the bin directory. 
    ``` 
    sudo mv kubectl /usr/local/bin/
    ``` 
    a. When prompted, enter `VMwarel!` as the password for `student01`. 
    
    
2.  Display the `kubectl` CLI version to ensure that the installation was successful. 
    ``` 
    kubectl version
    ``` 
    The output displays the client version `v1.33.0` and Kustomize version `v5.6.0`. 
    
    
3.  Get `kubectl` help. 
    ``` 
    kubectl --help
    ``` 
    
    

## Task 6: Enable kubectl CLI Autocompletion 

You enable `kubectl` CLI autocompletion to make `kubectl` easier to work with. 

1.  Insert the `kubectl` CLI autocompletion data into the `.bash_profile` files. 
    ``` 
    echo 'source <(kubectl completion bash)' >> ~/.bash_profile
    ``` 
    Autocompletion is enabled when you open a new terminal. 
    
    
2.  Reload the bash profile. 
    ``` 
    source ~/.bash_profile
    ``` 
    
    
3.  Enter `kubectl` followed by a space and then press **Tab** twice.  Autocompletion displays the available `kubectl` options. 
    > **NOTE**
    > In later labs, you can press **Tab** twice to autocomplete the commands. 

## Task 7: Create Context with VCF CLI 

You create a context with the VCF CLI. 

1.  Switch to the vSphere Client. 
2.  Click `supervisor01`. 
3.  Record the Kubernetes API Server IP address. 
4.  Switch to the Terminal. 
5.  Create context with VCF CLI using the supervisor IP address as the endpoint. 
    ``` 
    vcf context create --endpoint=<Kubernetes API Server IP> --insecure-skip-tls-verify
    ``` 
    Example: `vcf context create --endpoint=10.10.10.22 --insecure-skip-tls-verify` 
    
    
6.  At the *Provide a name for the context* prompt, enter `context01`. 
7.  At the *Provide username:* prompt, enter `administrator@vsphere.local`. 
8.  At the *Provide Password:* prompt, enter `VMware123!VMware123!`.  The logged in successfully message appears with the details of the contexts. 
9.  View the contents of the `kubeconfig` file. 
    ``` 
    cat ~/.kube/config
    ``` 
    
    
10. Switch to the Supervisor context. 
    ``` 
    vcf context use context01
    ```
    When you run this command for the first time, you might see the recommended plug-ins being installed for the `context01` context. [cite: 3, page 32]
    
    
11. List nodes in the Supervisor cluster. 
    ``` 
    kubectl get nodes
    ``` 
    
    
12. Query the cluster information. 
    ``` 
    kubectl cluster-info
    ``` 

