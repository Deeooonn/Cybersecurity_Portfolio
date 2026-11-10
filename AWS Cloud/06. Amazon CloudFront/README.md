Amazon CloudFront



In this lab, an amazon CloudFront distribution that uses a CloudFront domain name as the URL to distribute a publicly accessible image file stored in an Amazon Simple Storage Service (Amazon S3) bucket was created.





\###  Amazon CloudFront is a content delivery web service that integrates with other Amazon Web Services (AWS) products. Developers and businesses can use it to distribute content to end users with low latency (time delay), high data transfer speeds, and no minimum usage commitments.



Content is delivered through a worldwide network of data centers called edge locations. When a user requests data, the request is routed to the edge location that provides the lowest latency.



If content is cached at the edge location, CloudFront delivers it immediately. If it is not cached, CloudFront retrieves the data from an origin that you have defined, such as an Amazon S3 bucket.





\---Creating the S3 Bucket to store an image file.



Bucket was created with ACLs disabled, all public access blocked and the remaining default settings retained.

A random png or jpg image was downloaded locally and uploaded to the bucket.

Trying to access the image publicly using its URL failed as expected.





\---Creating and using the CloudFront distribution to serve the image file



\### Creating a CloudFront web distribution with origin access limits the access to your origin to only authenticated requests from CloudFront.

\### Origin access supports S3 buckets in all AWS Regions.

\### CloudFront provides two ways to send authenticated requests to an Amazon S3 origin: origin access control (OAC) and origin access identity (OAI).



\### CloudFront OAI provides similar functionality as OAC, but it doesn’t work for all scenarios. This is why AWS recommends using OAC. Scenarios that OAI does not support include the following:



&#x20;   Amazon S3 buckets in all AWS Regions, including opt-in Regions

&#x20;   Amazon S3 server-side encryption with AWS Key Management Service (AWS KMS) keys (SSE-KMS)

&#x20;   Dynamic requests (PUT, POST, or DELETE) to Amazon S3

&#x20;   New AWS Regions launched after December 2022



A simple distribution was created with mostly defaults.





\---Testing the distribution



Loading the page and serving the image file was so seamless and here we got no "access denied" error.

