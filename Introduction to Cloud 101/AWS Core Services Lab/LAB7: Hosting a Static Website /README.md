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

+   In the <b>AWS Management Console</b>, on the <b>Services</b> menu, choose <b>S3</b>.
+   Choose <b>Create bucket</b>
    
    An S3 bucket name is globally unique, and all AWS accounts share the namespace. After you create a bucket, no other AWS accountsin any AWS Regions can use the name of that bucket unless you delete the bucket.
    
    Thus, for this lab, you use a bucket name that includes a random number, such as _website-123_.

+   For <b>Bucket name</b>, enter `website-<123>` and replace _<123>_ with a random number.

    Public access to buckets is blocked by default. Because the files in your static website will need to be accessible through the internet, you must permit public access.

+   First Under <b>Object Ownership</b> choose <b>ACL enabled</b>.

+   Choose <b>Bucket owner preferred</b>.

+   Under <b>Block Public Access settings for this bucket</b>. Clear the check box for <b>Block all public access</b>, and then select the box that states <b>I acknowledge that the current settings may result in this bucket and the objects within becoming public</b>.

+   Under <b>Tags</b> Select <b>Add tag</b> and enter the following:

    +   <b>Key:</b> `Department`
    +   <b>Value:</b> `Marketing`
    
    You can use tags to add additional information to a bucket, such as a project code, cost center, or owner.

+   Choose <b>Create bucket</b>
    <img src="assets/Amazon S3 lab.PNG" alt=" " style="height: 100%; width:100%;"/>

+   In the <b>Buckets</b> section, choose the name of your new bucket.

+   Choose the <b>Properties</b> tab.
    
    <img src="assets/properties.PNG" alt=" " style="height: 100%; width:100%;"/>

You will now configure the bucket for static website hosting.

+   Scroll to the <b>Static website hosting</b> panel.

+   Choose <b>Edit</b>

    <img src="assets/edit website hosting.PNG" alt=" " style="height: 100%; width:100%;"/>

+   Configure the following settings:

    +   <b>Static web hosting:</b> Choose <b>Enable</b>.

    <img src="assets/static web hosting.PNG" alt=" " style="height: 100%; width:100%;"/>

    +   <b>Hosting type:</b> Choose <b>Host a static website</b>.
    +   <b>Index document:</b> Enter `index.html`

        +   <b>Note:</b> You must enter this value even though it is already displayed.

    +   <b>Error document:</b> Enter `error.html`

+   Choose <b>Save changes</b>

+   In the <b>Static website hosting</b> panel under <b>Bucket website endpoint</b>, choose the link.

    You receive a 403 Forbidden message because you have not yet configured the bucket permissions. Keep this tab open in your web browser so that you can return to it later.

    You have configured your bucket to host a static website.


####    Task 2: Uploading content to your bucket

In this task, you upload the static files to your bucket.

+   Right-click each of the following links, and download the files to your computer:
    Ensure that each file keeps the same file name, including the extension.

    +   <a href="src/index.html">index.html</a>
    +   <a href="src/script.js">script.js</a>
    +   <a href="src/style.css">style.css</a>

+   Return to the Amazon S3 console, and choose the <b>Objects</b> tab.
+   Choose <b>Upload</b>
+   Choose <b>Add files</b>
+   Choose the three files that you downloaded.
+   Choose <b>Upload</b>

Your files are uploaded to the bucket.

<img src="assets/upload.PNG" alt=" " style="height: 100%; width:100%;"/>

####    Task 3: Enabling access to the objects

Objects that are stored in Amazon S3 are private by default. This can help your organization's data remains secure.

In this task, you make the uploaded objects publicly accessible.

First, confirm that the objects are currently private.

+   Return to the browser tab that showed the _403 Forbidden_ message.
+   Refresh  the webpage.

If you accidentally closed this tab, go to the <b>Properties</b> tab, and in the <b>Static website hosting</b> panel, choose the <b>Bucket website endpoint</b> link again.

You should still see a _403 Forbidden_ message. This response is expected! This message indicates that your static website is being hosted by Amazon S3 but that the content is private.

You can make Amazon S3 objects public through two different ways:

+   To make either a whole bucket public, or a specific directory in a bucket public, use a _bucket policy_.
+   To make individual objects in a bucket public, use an _access control list (ACL)_.

It is normally safer to make individual objects public because doing so avoids accidentally making other objects public. However, if you know that the entire bucket contains no sensitive information, you can use a bucket policy.

You now configure the individual objects to be publicly accessible.

+   Return to the web browser tab with the Amazon S3 console (but do not close the website tab).
+   Select  all three objects.
+   In the <b>Actions</b> menu, choose <b>Make public</b>.

A list of the three objects is displayed.

+   Choose <b>Make public</b>

Your static website is now publicly accessible.
<img src="assets/make public.PNG" alt=" " style="height: 100%; width:100%;"/>

+   Return to the web browser tab that has the _403 Forbidden_ message.
+   Refresh  the webpage.

You should now see the static website that is being hosted by Amazon S3.

####    Task 4: Updating the website

You can change the website by editing the HTML file and uploading it again to the S3 bucket.

Amazon S3 is an _object storage service_, so you must upload the whole file. This action replaces the existing object in your bucket. You cannot edit the contents of an object; instead, you must replace the whole object.

+   On your computer, load the <b>index.html</b> file into a text editor (for example, Notepad or TextEdit).

+   Find the text <b>Served from Amazon S3</b>, and replace it with `Created by <YOUR-NAME>`, substituting your name for <YOUR-NAME> (for example, _Created by Jane_).
+   Save the file.
+   Return to the Amazon S3 console, and upload the <b>index.html</b> file that you just edited.
+   Select <b>index.html</b>, and in the <b>Actions</b> menu, choose the <b>Make public</b> option again.
+   Return to the web browser tab with the static website, and refresh  the page.

Your name should now be on the page.

Your static website is now accessible on the internet. Because it is hosted on Amazon S3, the website has high availability and can serve high volumes of traffic without using any servers.

You can also use your own domain name to direct users to a static website that is hosted on Amazon S3. To accomplish this, you could use the Amazon Route 53 Domain Name System (DNS) service in combination with Amazon S3.

####    Submitting your work

+   At the top of these instructions, choose <b>Submit</b> to record your progress and when prompted, choose <b>Yes</b>. 
     
+   If the results don't display after a couple of minutes, return to the top of these instructions and choose <b>Grades</b> 

+   To find detailed feedback on your work, choose <b>Details</b> and then choose <b>View Submission Report</b>.

####    Lab complete