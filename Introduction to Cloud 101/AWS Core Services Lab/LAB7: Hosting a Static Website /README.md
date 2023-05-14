#   LAB7: Hosting a Static Website

### Lab overview and objectives

Static websites have fixed content with no backend processing. They can contain HTML pages, images, style sheets, and all files that are needed to render a website. However, static websites do not use server-side scripting or a database. If you want your static webpages to provide interactivity and run programming logic, you can use JavaScript that runs in the user's web browser.

You can easily host a static website on Amazon Simple Storage Service (Amazon S3) by uploading the content and making it publicly accessible. No servers are needed, and you can use Amazon S3 to store and retrieve any amount of data at any time from anywhere on the web. _Click to [Learn more...](https://awseducate.instructure.com/courses/768/assignments/3159?module_item_id=13575)_

After completing this lab, you will know how to:

+   Create a bucket in Amazon S3
+   Upload content to your bucket
+   Enable access to the bucket objects
+   Update the website 

####    Task 1: Creating a bucket in Amazon S3
+   In the AWS Management Console, on the Services menu, choose S3.

+   Choose Create bucket

An S3 bucket name is globally unique, and all AWS accounts share the namespace. After you create a bucket, no other AWS accountsin any AWS Regions can use the name of that bucket unless you delete the bucket.

Thus, for this lab, you use a bucket name that includes a random number, such as website-123.
+   For Bucket name, enter website-<123> and replace <123> with a random number.



Public access to buckets is blocked by default. Because the files in your static website will need to be accessible through the internet, you must permit public access.

+   First Under Object Ownership choose ACL enabled.

+   Choose Bucket owner preferred.

+   Under Block Public Access settings for this bucket. Clear the check box for Block all public access, and then select the box that states I acknowledge that the current settings may result in this bucket and the objects within becoming public.

+   Under Tags Select Add tag and enter the following:

    +   Key: Department
    +   Value: Marketing
    You can use tags to add additional information to a bucket, such as a project code, cost center, or owner.

+   Choose Create bucket
    <img src="Amazon S3 lab.PNG" alt=" " style="height: 100%; width:100%;"/>

In the Buckets section, choose the name of your new bucket.

+   Choose the Properties tab.
<img src="properties.PNG" alt=" " style="height: 100%; width:100%;"/>
You will now configure the bucket for static website hosting.

+   Scroll to the Static website hosting panel.

+   Choose Edit

    <img src="edit website hosting.PNG" alt=" " style="height: 100%; width:100%;"/>

+   Configure the following settings:

    +   Static web hosting: Choose Enable.

    <img src="static web hosting.PNG" alt=" " style="height: 100%; width:100%;"/>

+   Hosting type: Choose Host a static website.
+   Index document: Enter index.html

    Note: You must enter this value even though it is already displayed.
    +   Error document: Enter error.html
+   Choose Save changes

+   In the Static website hosting panel under Bucket website endpoint, choose the link.

You receive a 403 Forbidden message because you have not yet configured the bucket permissions. Keep this tab open in your web browser so that you can return to it later.

You have configured your bucket to host a static website.


####    Task 2: Uploading content to your bucket
In this task, you upload the static files to your bucket.

+   Right-click each of the following links, and download the files to your computer:
Ensure that each file keeps the same file name, including the extension.

  +   index.html
    +   script.js
    +   style.css

   

Return to the Amazon S3 console, and choose the Objects tab.
Choose Upload
Choose Add files
Choose the three files that you downloaded.
+   Choose Upload
Your files are uploaded to the bucket.

<img src="upload.PNG" alt=" " style="height: 100%; width:100%;"/>

####    Task 3: Enabling access to the objects
Objects that are stored in Amazon S3 are private by default. This can help your organization's data remains secure.

In this task, you make the uploaded objects publicly accessible.
First, confirm that the objects are currently private.

+   Return to the browser tab that showed the 403 Forbidden message.
+   Refresh  the webpage.
 If you accidentally closedthis tab, go to the Properties tab, and in the Static website hosting panel, choose the Bucket website endpoint link again.

You should still see a 403 Forbidden message. This response is expected! This message indicates that your static website is being hosted by Amazon S3 but that the content is private.

You can make Amazon S3 objects public through two different ways:

+   To make either a whole bucket public, or a specific directory in a bucket public, use a bucket policy.
+   To make individual objects in a bucket public, use an access control list (ACL).
It is normally safer to make individual objects public because doing so avoids accidentally making other objects public. However, if you know that the entire bucket contains no sensitive information, you can use a bucket policy.

You now configure the individual objects to be publicly accessible.

+   Return to the web browser tab with the Amazon S3 console (but do not close the website tab).
+   Select  all three objects.
+   In the Actions menu, choose Make public.
A list of the three objects is displayed.

+   Choose Make public
Your static website is now publicly accessible.
<img src="make public.PNG" alt=" " style="height: 100%; width:100%;"/>

+   Return to the web browser tab that has the 403 Forbidden message.
+   Refresh  the webpage.
You should now see the static website that is being hosted by Amazon S3.

####    Task 4: Updating the website
You can change the website by editing the HTML file and uploading it again to the S3 bucket.

Amazon S3 is an object storage service, so you must upload the whole file. This action replaces the existing object in your bucket. You cannot edit the contents of an object; instead, you must replace the whole object.

+   On your computer, load the index.html file into a text editor (for example, Notepad or TextEdit).
+   Find the text Served from Amazon S3, and replace it with Created by <YOUR-NAME>, substituting your name for <YOUR-NAME> (for example, Created by Jane).
+   Save the file.
+   Return to the Amazon S3 console, and upload the index.html file that you just edited.
+   Select  index.html, and in the Actions menu, choose the Make public option again.
+   Return to the web browser tab with the static website, and refresh  the page.
Your name should now be on the page.
<img src="website.PNG" alt=" " style="height: 100%; width:100%;"/>

Your static website is now accessible on the internet. Because it is hosted on Amazon S3, the website has high availability and can serve high volumes of traffic without using any servers.

You can also use your own domain name to direct users to a static website that is hosted on Amazon S3. To accomplish this, you could use the Amazon Route 53 Domain Name System (DNS) service in combination with Amazon S3.
####    `End lab`