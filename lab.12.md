Lab 12 Creating a Provider Content
Library

Objective and Tasks
Create a provider content library in the provider management portal:
1. (Optional) Log In to the VCF Automation Provider Management Portal
2. Create a Provider Content Library
3. Uploading an OVA to Content Library
Task 1: (Optional) Log In to the VCF Automation Provider
Management Portal
You log in to the VCF Automation Provider Management Portal.
1. On the Google Chrome bookmarks bar, right-click VCF Automation and select Open in
new incognito window.
a. If the Your connection is not private message appears, click Advanced
and click Proceed to sa-vaa01.vcf.sddc.local(unsafe).
b. Under Organization name, enter system
c. Log in to the VCF Automation Provider Management Portal.
 From the first drop-down menu, select Log in with local account.
 User name: admin
 Password: VMware123!VMware123!
d. Leave the VCF Automation Provider Management Portal open for the next task.

49

Task 2: Create a Provider Content Library
You create a provider content library.
1. In the Provider Management portal, click Content Libraries under Infrastructure.

2. Click CREATE CONTENT LIBRARY.
The Create a Content Library page appears.
3. Specify the details for the new content library.
4. In the Name text box, enter Provider_CL
5. Click NEXT
6. From the Region drop-down menu, select region1.
7. Under Storage Class, select supervisor-storage-policy.
a. Click NEXT.
8. In the Summary section, click CONFIRM.
Wait for the content library to be created.
9. Verify that the content library status is Ready.
Task 3: Uploading an OVA to Content Library
1. Click Provider_CL.
2. Click Content Library Items.
3. Click UPLOAD.

50
4. Click the Upload Icon link to select a source file.
5. Select the ubuntu-24.04-server.ova file from Recent and click Open.
6. Verify that Provider_CL is selected in the Content Library drop-down menu.
7. Verify that the Name text box is ubuntu-24.04-server.
8. Click SUBMIT.
9. Verify that the ubuntu-24.04-server status is Ready.
10. Close the Chrome browser.