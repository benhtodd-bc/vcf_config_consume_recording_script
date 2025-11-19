Lab 10 Creating an Organization

Objective and Tasks
Create an organization for an organization user:
1. (Optional) Log In to the VCF Automation Provider Management Portal
2. Create an Organization
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
Task 2: Create an Organization
You create an organization for a tenant user.
1. Click Organizations under Infrastructure.
2. Click CREATE ORGANIZATION.

41

3. In the Name text box, enter Learning_Org
a. Click CREATE AND CONTINUE.
4. Specify the Region and Supervisor, in the Assign a region Quota section.
a. From the Region drop-down menu, select region1.
b. From the Supervisor drop-down menu, select Supervisor01.
5. In the Zones section, click ADD.
The Add a zone window appears.
a. Enter the values in the Add a zone window.
Zone Select vspherezone01.
CPU Limit 100 GHz
CPU Reservation Leave the default value.
Memory Limit 128 GB
Memory Reservation Leave the default value.

b. Click SAVE.
c. Click ASSIGN AND CONTINUE.

6. Under VM Classes, select the best-effort-large, best-effort-medium, and best-effort-
small checkboxes.

7. Under Storage Classes, select the supervisor-storage-policy checkbox.
a. Click ASSIGN AND CONTINUE.
8. Under Add First User, enter the details.
User name student1
Password VMware123!VMware123!
Confirm password VMware123!VMware123!
Role Select Organization Administrator.

a. Click ADD USER AND FINISH.
9. Verify that Learning_Org is created successfully.

42
IMPORTANT
To finish setting up an organization, you must configure regional networking, which is
covered in the next lab.

10. Log out as admin user.
a. Click the admin user drop-down menu from the top-right corner.
b. Click Log out.