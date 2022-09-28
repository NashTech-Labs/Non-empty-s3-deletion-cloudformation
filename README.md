# s3-deletion-using-cloudformation-template

If you have created an s3 bucket with versioning enabled using cloud formation and you have also uploaded some objects in that bucket. You havecreated Access points for that bucket manually. So now when you try to delete the cloudformation stack it wont get deleted because its non-empty and access points are associated with the bucket.

For deleting it you must have to empty the bucket manually and delete its access points which are created manually. To automate that task this stack needs to be created .

I Am passing the BucketName and the Account Id to the custom resource lambda function which I created during the stack creation time. Lambda will take these inputs and delete the bucket contents and associated access points.

Custom resource will trigger and delete the layer once i’ll receive the Request Type is delete from Cloudformation Template

