# Lab 19 Deploying an Application

## Objective and Tasks

Creating an application in learning_org:

1. Deploy an Application

### Task 1: Deploy an Application
1. Click the Terminal icon from the taskbar to open the command line.

2. Export the ```kubeconfig``` file.

    ```export KUBECONFIG=/home/student01/Downloads/vks-cluster-1-kubeconfig.yaml```

3. Apply the configuration file.

    ```kubectl apply -f Downloads/YAML-files/nginx-service-sc.yaml```

4. List the deployments.
    
    ```kubectl get pods -n nginx-ns```

5. Lists the services on ngnix-ns.

    ```kubectl get svc -n nginx-ns```

6. Record the ```EXTERNAL-IP``` assigned to the nginx-service.

7. Open ```Google Chrome``` from the taskbar.

    Open a new tab in Google Chrome.

    *a*. In the address bar, enter ```http://EXTERNAL-IP``` and press ```Enter```

        Example: ```http://10.10.10.36```

        The Welcome to nginx! page appears.

    *b*. Click ```X``` to close the ```nginx``` tab.

    *c*. Click ```X``` to close the ```Chrome``` browser.