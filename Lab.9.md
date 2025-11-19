Lab 9 Creating a Region

Objective and Tasks
Create a region and verify the region details:
1. (Optional) Log In to the VCF Automation Provider Management Portal
2. Create a Region
3. Verify Region Details
Task 1: (Optional) Log In to the VCF Automation Provider
Management Portal
You log in to the VCF Automation Provider Management Portal.
1. On the Google Chrome bookmarks bar, right-click VCF Automation and select Open in
new incognito window.
a. If the Your connection is not private message appears, click Advanced
and click Proceed to sa-vaa01.vcf.sddc.local(unsafe).
i. Under Organization name, enter system
b. Log in to the VCF Automation Provider Management Portal.
 From the first drop-down menu, select Log in with local account.
 User name: admin
 Password: VMware123!VMware123!
c. Leave the VCF Automation Provider Management Portal open for the next task.
Task 2: Create a Region
You create a region and map it to a vSphere Supervisor and NSX Manager instance.
1. In the Provider Management portal, click Infrastructure Overview on the left pane.

38
2. In the Get Started section, click START next to Create Region.

3. In the Name text box, enter region1

4. From the NSX Local Manager drop-down menu, select sa-wld01-nsxt-
vip.vcf.sddc.local.

5. In the Supervisor(s) section, select the supervisor01 checkbox.
6. Select the storage policy under storage classes.
a. Click > to browse policies.
b. In Storage Class(es), select supervisor-storage-policy.
7. Click SUBMIT.
Task 3: Verify Region Details
You verify the region from the organization portal.
1. Click Regions under Infrastructure.
2. Click region1.
a. The region1 page opens.
3. Verify the vSphere Supervisor details.
a. Click Supervisors on the region1 page.
b. Expand Supervisor01 by clicking the two right arrows.
c. Verify the vCenter and Zone details that appear in the Supervisor pane.

39

4. Click VM Classes.
a. Verify the VM classes that are precreated by default.
5. Click Storage Classes.
a. Verify that supervisor-storage-policy is attached to region1.