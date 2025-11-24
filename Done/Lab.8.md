# Lab 8 Configuring an Identity Provider in VCF Automation

## Objective and Tasks
Configure an LDAP identity provider and test the connection:

1. Log In to the VCF Automation Provider Management Portal
2. Configure an Open LDAP Connection
3. Test the Connection

### Task 1: Log In to the VCF Automation Provider Management Portal
You log in to the VCF Automation Provider Management Portal.

1. On the Google Chrome bookmarks bar, right-click VCF Automation

    a. Click Open in new incognito window.

    b. If the Your connection is not private message appears, click Advanced and click Proceed to sa-vaa01.vcf.sddc.local(unsafe).
    
    c. Under Organization name, enter system
    
    d. Log in to the ```VCF Automation Provider``` Management portal
        
    * **User name:** ```admin```
        
    * **Password:** ```VMware123!VMware123!```

2. If your first login fails because the token has expired, close the Chrome browser.

    a. On the Chrome bookmarks bar, right-click ```VCF Automation``` and select ```Open in new incognito window```.

3. Click ```GET STARTED``` in the Manual Setup title.
    
4. Review the VCF Automation infrastructure.

    a. Click ```Infrastructure Overview``` on the left

    b. Verify that no organizations or regions currently exist.

5. Leave the VCF Automation Provider Portal open for the next task.

## Task 2: Configure an Open LDAP Connection
You configure an identity provider using the LDAP protocol.

1. On the ```Provider Management page```, click ```Identity Providers``` under ```Administration```.

2. Click the ```LDAP``` tab.

3. Click ```CONFIGURE```.

4. On the ```Edit LDAP``` page, configure the ```Open LDAP``` settings.

| Option | Action |
| :------- | :------ |
| Server | dc.vclass.local |
| port | 636|
| Base Distinguished Name | dc=vclass,dc=local |
| Connector type | Open LDAP |
| Use SSL | Turn on the toggle to enable. |
| Authentication Method | Leave Simple selected. |
| User Name | administrator@vclass.local |
| Password | VMware1! |

5. Click ```SAVE```.

6. In the ```Trust Certificate``` window, click ```TRUST SELECTED``` to trust the certificate.


## Task 3: Test the Connection
You test to verify the identity provider connection.

1. On the ```Provider Management``` page, ensure that ```Identity Providers``` is selected under Administration.

2. Click ```TEST```.
The ```Test LDAP``` window appears.

a. Enter ```VMware1!``` as the password.

b. Click ```TEST```.

3. Verify that the ```Test LDAP``` window appears as ```Connected``` with a green tick.

4. Click ```X``` to close the ```Test LDAP``` window.

5. Click ```SYNC```.

    The ```Synchronize LDAP``` window appears.

    a. Click ```SYNC```.

    The ```Synchronization with LDAP has started``` message appears.

    b. Click ```Recent Tasks``` to review the synchronized System LDAP

6. Click ```Recent Tasks```.

a. Verify that the Synchronized System LDAP entry status appears as Succeeded.