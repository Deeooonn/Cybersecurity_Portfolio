Amazon Simple Storage Service (S3) Buckets



In this lab, A bucket was created, an object was uploaded to the bucket, an object was made public, connectivity was tested from the EC2 instance, a bucket policy was created and finally, versioning was explored.



\---Create a bucket and upload an object to the bucket.

A unique bucket name was assigned, ACLs and Object Writer were enabled in the object ownership section.



A file was uploaded using the upload wizard



\---Make an object public



\## Because security is an important subject in Amazon S3, it is important to test a bucket's security before connecting it to an EC2 instance.



\## Ensure to configure permissions on the bucket and object to tests accessibility.



First, to ensure the object is private by default, it was first accessed.



The object in the bucket was selected and the object URL was copied and pasted into an address bar



The search returned an error indicating privacy of the object by default



An attempt to make object public "make public using ACL" using the object action dropdown, it failed as the public access settings for the bucket was blocked. This had to be unblocked



The "Block Public Access" for the bucket was deselected



Object was successfully made public using ACL



Object was accessible from the url





\---Test Connectivity from the EC2 Instance

A Bastion hosting instance was connected to and a session was opened

In the terminal window, all buckets connected to that instance were listed and all objects in the bucket were also listed.



Copying object to the bucket failed.





\---Create a bucket Policy

Added a new object to the bucket and trying to publicly access the bucket failed.



An "EC2InstanceProfileRole" ARN under IAM Roles, an S3 bucket ARN and the AWS Policy Generator were used to create the policy.



\## ARN: Amazon Resource Name is a standard way to refer to resources within AWS



The policy type "Bucket policy" was selected, the action set to "allow" and the "GetObject" and "PutObject" were actions selected in the Policy Generator window.



Bucket policy for the bucket was edited by pasting the generated JSON into the bucket policy window.



A file can now be copied/put from EC2 instance to the S3 bucket

A command to also retrieve(GetObject) from an S3 bucket to the EC2 instance then worked.



The page of the file attempted to be access publicly still displays an error message because the Bucket Policy only gave rights to the principal called EC2InstanceProfileRole.



A new statement was added to the JSON file to resolve this.



The file was then accesible from the web browser.



\---Explore Versioning

\## Versioning is a means of keeping multiple variants of an object in the same bucket. You can use versioning to preserve, retrieve, and restore every version of every object stored in your Amazon S3 bucket. With versioning, you can easily recover from both unintended user actions and application failures.



\## For auditing and compliance reasons you need to enable versioning on your reportbucket. Versioning should protect the reports in the reportbucket against accidental deletion.



Bucket versioning was enabled under "bucket properties"



Show version was toggled under the "objects" section



A modified version of the sample file was uploaded to the bucket



Refreshing the URL of the sample file displayed the modified content



Selecting the sample text file and viewing the versions tab displays the versions of the file



Trying to view older version using the URL returned an error



\## This is expected because the bucket policy you created only allows permission to access the latest version of the object. In order to access a previous version of the object, you need to update your bucket policy to include the “s3:GetObjectVersion” permission. Below is an example bucket policy with the additional “s3:GetObjectVersion” action added that allows you to access the older version using the link.



\## Now you can view the available versions of each object and identify which version is the latest. Notice the new-report.png object only has one version and the version ID is null. This is because the object was uploaded before versioning was enabled on this bucket.



\## you can now choose the version name link to navigate directly to that version of the object in the console.



The "Show Versions" was toggled off and the sample file deleted.



Toggling on the "Show Versions" displayed the deletion mark and all versions.



\## The "delete marker" is the current version



The object with the deletion marker was permanently deleted and "Show Versions" toggled off



The sample txt file version then returned to the bucket



The latest version "Not delete marker version" was also deleted and the older version was then restored as the remaining file in the bucket, allowing the sample txt file object's first version to be viewable using its URL.

