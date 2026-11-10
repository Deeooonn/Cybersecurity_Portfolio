AWS Identity and Access Management (IAM)



In this lab, users and groups were explored. Users were added to groups and the sign-in and user permissions were tested in a business setting.



\### A policy defines what actions are allowed or denied for specific AWS resources. This policy is granting permission to List and Describe information about EC2, Elastic Load Balancing, CloudWatch and Auto Scaling. This ability to view resources, but not modify them, is ideal for assigning to a Support role.





User1 was added to the S3-Support group

User2 was added to the EC2-Support group

User3 was added to the EC2-Admin group



\*\*\*\*\*\*\*\*\*ALL according to their business functions.



\---Sign-In and Test User Permissions



The IAM dashboard contains the Sign-In URL AWS



User1 has access to S3-support group which allows access to view the S3 bucket list and the content in the buckets.

Trying to access EC2 instances threw an exception (error).



User 2 did not have the permission to stop an instance it was allowed to view. This is because the user group did not allow it. Access to S3 was also denied.





User 3 successfully stopped the instance.



\### Inheritance of permissions assigned to user groups is a property the AWS uses to make centralized management smooth and scalable.

