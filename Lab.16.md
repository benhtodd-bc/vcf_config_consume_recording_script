Lab 16 Creating a Virtual Machine

Objective and Tasks
Create a virtual machine in learning_org:
1. (Optional) Log In to the VCF Automation Organization Portal
2. Create a Virtual Machine from the Organization Portal
Task 1: Log In to the VCF Automation Organization Portal
You log in to the VCF Automation Organization Portal.
1. On the Google Chrome bookmarks bar, right-click VCF Automation and select Open in
new incognito window.
a. If the Your connection is not private message appears, click Advanced
and click Proceed to sa-vaa01.vcf.sddc.local(unsafe).
b. Under Organization name, enter learning_org
c. Log in to the VCF Automation Organization Portal.
 From the first drop-down menu, select Log in with local account.
 User name: student1
 Password: VMware123!VMware123!
d. Leave the VCF Automation Organization Portal open for the next task.
Task 2: Create a Virtual Machine from the Organization Portal
You create the virtual machine in learning_org.
1. In the Organization portal, click Build & Deploy.
2. Click Virtual Machine

61

3. Click + CREATE VM
4. In the New Virtual Machine wizard, select Deploy from OVF and click NEXT.
5. In the VM Name text box, enter vm-ubuntu
6. From the Zone drop-down menu, select vspherezone01.
7. Select ubuntu-24.04-server under VM Image.
a. Scroll-down to select best-effort-small under VM Class.
8. Click NEXT.
9. Scroll down to the Guest Customization and verify that cloud-init is selected.
10. Under GUIDE INPUTS, click CREATE NEW USER.
The Create New User window opens.
Option Value
Username ubuntu-user
Password VMware123!VMware123!
Confirm Password VMware123!VMware123!
Default Sudo Enable

a. Click SAVE.
b. Click the SSH Password Authentication drop-down menu and select Enable.
c. Click NEXT.
11. Under Global Network Settings, click NEXT.
12. Click DEPLOY VM.
The virtual machine deployment will take about 5 minutes.
13. Click the virtual machine Name (vm-ubuntu) in the Name column to verify the VM Details.