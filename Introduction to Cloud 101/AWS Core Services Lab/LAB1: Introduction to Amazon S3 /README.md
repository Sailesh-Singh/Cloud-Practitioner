 #   Lab 1: Introduction to Amazon Simple Storage Service (Amazon S3)

### Lab overview and objectives

This lab teaches you the basic feature functionality of Amazon Simple Storage Service (Amazon S3) using the AWS Management Console. _Click to [Learn more ...](https://awseducate.instructure.com/courses/768/assignments/3145)_

After completing this lab, you will know how to:
    
+   Create a bucket in Amazon S3
+   Add an object to a bucket
+   Manage access permissions on an object and a bucket
+   Create a bucket policy
+   Use bucket versioning

####   Duration
This lab requires approximately **60** minutes to complete. You will have a total time of **240** minutes to complete this lab.


####    Task 1: Creating a bucket 
<img src="./assets/Lab1_AmazonS3_T1_Start-Lab.png" alt="Lab1_AmazonS3_T1_Start-Lab" width="50%" height="80%" ><img src="./assets/Lab1_AmazonS3_T1_AWS_Management_Console-Services.png" alt="Lab1_AmazonS3_T1_AWS_Management_Console-Services" width="50%" height="80%" >
<small><b>*_Start and Launch AWS Management Console_*</b></small>

+   At the upper left of the AWS Management Console, on the <b>Services</b> menu, choose <b>S3</b>.
+   Choose <b>Create bucket</b>.
+   In the  <b>General configuration</b>  section, enter the following as the  <b>Bucket name</b>: `reportbucket(NUMBER)`

    Example bucket name: `reportbucket789`
+   Leave <b>Region</b> at its default value.
+   Click  <b>Create bucket</b>.

<img src="./assets/Lab1_AmazonS3_T1_Configure-bucket.png" alt="Lab1_AmazonS3_T1_Configure-bucket.png" width="50%" height="80%" ><img src="./assets/Lab1_AmazonS3_T1_bucket-created.png" alt="Lab1_AmazonS3_T1_bucket-created" width="50%" height="80%" >
<small><b>*_Configure and Create bucket_*</b></small>

####    Task 2: Uploading an object to the bucket
Now that you have created a bucket for your report data, you are ready to work with objects.

+   Right-click the following link:  [new-report.png](./assets/new-report.png). Choose  <b>Save link as</b>, and save the file to your desktop.

+   In the  <b>S3 Management Console</b>, find and select the bucket name that starts with  <b>reportbucket</b>. 
+   Choose  <b>Upload</b>
+   Choose  <b>Add files</b>
+   Browse to and select the  <b>new-report.png</b>  file that you downloaded previously. 
+   At the bottom of the page, choose  <b>Upload</b>

[<img src="assets/Lab1_AmazonS3_T1_upload_new-report.png" alt="Lab1_AmazonS3_T1_upload_new-report" width="100%" height="100%" >]()

Your file is successfully uploaded when the green bar indicating  <b>Upload succeeded</b>  appears.

+   In the <b>Upload: status </b> section in the upper right, choose  <b>Close</b>

[<img src="assets/Lab1_AmazonS3_T1_uploaded_new-report.png" alt="Lab1_AmazonS3_T1_uploaded_new-report" width="100%" height="100%" >]()
<small><b>*_Upload Status_*</b></small>

