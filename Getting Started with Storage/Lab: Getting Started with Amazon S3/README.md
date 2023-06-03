#   Lab: Getting Started with Amazon S3

### Lab overview and objectives

In this lab, we use some of the Amazon Simple Storage Service (Amazon S3) features that we just learned about to create a static website. _Click to [Learn more ...](https://awseducate.labs.awsevents.com/sa/lab/arn%3Aaws%3Alearningcontent%3Aus-east-1%3A470679935125%3Ablueprintversion%2FCUR-TF-100-EDSTOR-1%2F01-lab-s3%3A1.0.2-cff75cb4/en-US)_

<details>
<summary><b>Read More</b></summary>

+   Static websites can contain HTML pages, images, style sheets, and all files that are needed to render a website. Static websites do not use server-side scripting or a database. However, they may contain client-side scripts that run in a user’s web browser.

+   We can host a static website on Amazon S3 by uploading the content and making it readable by users. No servers are needed, and we can use Amazon S3 to store and retrieve any amount of data at any time from anywhere on the web.
</details>
<br>

After completing this lab, we will know how to do the following:

+   Create a bucket in Amazon S3.
+   Configure a bucket to host a static website.
+   Upload content to a bucket.
+   Turned on public access to bucket objects.
+   Securely share a bucket object using a presigned URL.
+   Secure a bucket using a bucket policy.
+   Update the website.
+   View object versions in the Amazon S3 console.

####   Duration
This lab requires approximately **30 minutes** to complete. We will have a total time of **180 minutes** to complete this lab.

#### Prerequisites

This lab requires the following:

+   A notebook computer running Microsoft Windows, macOS, or Linux (Ubuntu, SUSE, or Red Hat)
+   An internet connection
+   For Microsoft Windows users, administrator access to the computer

><b>_Note:</b> This lab is incompatible with Internet Explorer 11. Use a different browser to launch this lab._

---

####    Task 1: Creating a bucket in Amazon S3

In this task, we create an S3 bucket and configure it for static website hosting.

+   In the **AWS Management Console**, on the **Services** menu, choose **S3**.

+   Choose **Create bucket**

    An S3 bucket name is globally unique, and all AWS accounts share the namespace. After we create a bucket, no other AWS accounts in any AWS Regions can use the name of that bucket unless we delete the bucket.

    For this lab, we use a bucket name that includes a random number, such as **website-123**.

+   For **Bucket name**, enter `website-<123>` and replace _<123>_ with a random number.

    Public access to buckets is blocked by default. Because the files in our static website will need to be accessible through the internet, we must permit public access.

+   For **Object Ownership**, choose **ACLs enabled**.

+   Choose **Bucket owner preferred**.

+   For **Block Public Access settings for this bucket**, clear the check box for **Block _all_ public access**, and then select the box that states **I acknowledge that the current settings might result in this bucket and the objects within becoming public**.

+   For **Bucket Versioning**, choose **Enable**.

    >Note: Once we turn on (enable) bucket versioning, we can’t turn it off.

+   For **Tags**, choose **Add tag**, and enter the following:

    +   **Key:** `Department`
    +   **Value:** `Marketing` we can use tags to add additional information to a bucket, such as a project code, cost center, or owner.

+   Choose **Create bucket**

+   In the **Buckets** section, choose the name of our new bucket.

+   Choose the **Properties** tab.


####    Task 2: Configuring a static website on Amazon S3
we will now configure the bucket for static website hosting.

+   Scroll to the **Static website hosting** panel.
+   Choose **Edit**

+   Configure the following settings:

    +   **Static web hosting:** Choose **Enable**.
    +   **Hosting type:** Choose **Host a static website**.
    +   **Index document:** Enter `index.html`
    +   **Error document:** Enter **error.html** 
    **Note:** we must enter `index.html` and `error.html` even though they are already displayed.

+   Choose **Save changes**

+   In the **Static website hosting** panel under **Bucket website endpoint**, choose the link.

    we receive a _403 Forbidden_ message because we have not yet configured the bucket permissions. Keep this tab open in our web browser so that we can return to it later.

    we have configured our bucket to host a static website.


####    Task 3: Uploading content to our bucket

In this task, we upload the static files to our bucket.

+   Choose (right-click) each of the following links, and download the files to our computer:

    Ensure that each file keeps the same file name, including the extension.

    +   <a href="./src/index.html" target="_blank">index.html</a>
    +   <a href="./src/script.js" target="_blank">script.js</a>
    +   <a href="./src/style.css" target="_blank">style.css</a>

+   Return to the Amazon S3 console, and choose the **Objects** tab.
+   Choose **Upload**
+   Choose **Add files**
+   Choose the three files that we downloaded.
+   Choose **Upload**

our files are uploaded to the bucket.

+   Choose **Close**


####    Task 4: Turning on public access to the objects

Objects that are stored in Amazon S3 are private by default. This setting helps keep our organization’s data secure.

In this task, we make the uploaded objects publicly accessible so users can view our website.

First, confirm that the objects are currently private.

+   Return to the browser tab that showed the _403 Forbidden_ message.
+   Refresh the webpage.

If we accidentally closed this tab, go to the **Properties** tab, and in the **Static website hosting** panel, choose the **Bucket website endpoint** link again.

We should still see a _403 Forbidden_ message. This response is expected! This message indicates that our static website is being hosted by Amazon S3 but that the content is private.

+   We can make Amazon S3 objects public through two different ways:

    +   To make either a whole bucket public or a specific directory in a bucket public, use a bucket policy.

    +   To make individual objects in a bucket public, use an access control list (ACL). It is normally safer to make individual objects public because doing so avoids accidentally making other objects public. However, if we know that the entire bucket contains no sensitive information, we can use a bucket policy.

    We now configure the individual objects to be publicly accessible.

+   Keep the website tab open, and return to the web browser tab with the Amazon S3 console.
+   Choose all three objects.
+   In the **Actions** menu, choose **Make public using ACL**.

A list of the three objects is displayed.
+   Choose **Make public**

Our static website is now publicly accessible.
+   Choose **Close**
+   Return to the web browser tab that has the _403 Forbidden_ message.
+   Refresh the webpage.

We should now see the static website that is being hosted by Amazon S3.

Now we know how to share objects with everyone by making them public. However, there may be times when we need to share an individual object for a limited amount of time. In the next task, we learn how to temporarily share an object.


####    Task 5: Securely sharing an object using a presigned URL

When we need to temporarily and securely share an object with a person or group of people, we can create a presigned URL. When we create the URL, we must configure how long the URL will be valid. Then, we can share this URL with the users who should have access to the object.

As long as the presigned URL is valid, anyone who has it can get to the object. Avoid keeping the URL active longer than necessary, and only share the URL with people we trust.

+   Choose (right-click) the following link, and download the file to our computer: Ensure that the file keeps the same file name, including the extension.

    +   <a href="./assets/new-report.png">new-report.png</a>

+   Return to the Amazon S3 console, and choose the **Objects** tab.
+   Choose **Upload**
+   Choose **Add files**
+   Choose the file that we downloaded.
+   Choose **Upload**

We have uploaded our file to the bucket.

+   Choose **Close**

    Like when we first uploaded the website files, the **new-report.png** file is private by default. This time, instead of making the object public, we create a presigned URL to access the file.

+   In the **Objects** tab, choose **new-report.png**.
+   From the **Actions** menu, select **Share with a presigned URL**

+   In the pop-up window, configure the **Time interval until the presigned URL expires:**
    +   Choose **Minutes**

+   Choose **Create presigned URL**

+   From the banner at the top of the page, choose **Copy presigned URL**.

+   Open a new browser tab, and paste the URL we copied into the address bar.

    A report is displayed in the web browser.

    If we wait 5 minutes and use the link again, we will find that the URL has expired and no longer works.


####    Task 6: Using a bucket policy to secure your bucket

You want to protect your website files and make sure that no one can delete them. To do this, you apply a bucket policy that denies delete privileges on your website files.

+   Return to the Amazon S3 console, and choose the **Permissions** tab.
+   Under **Bucket policy**, choose **Edit**
+   Copy the following policy text. In the **Policy** text editor, replace the existing policy text with this text:

```
    {
        "Version": "2012-10-17",
        "Id": "MyBucketPolicy",
        "Statement": [
            {
                "Sid": "BucketPutDelete",
                "Effect": "Deny",
                "Principal": "*",
                "Action": "s3:DeleteObject",
                "Resource": [
                    "arn:aws:s3:::<bucket-name>/index.html",
                    "arn:aws:s3:::<bucket-name>/script.js",
                    "arn:aws:s3:::<bucket-name>/style.css"
                ]
            }
        ]
    }
```
This policy prevents everyone from deleting the three files that make our website work.

+   Next, you update the text in the policy editor. In the following lines of code in the policy editor, replace the _<bucket-name>_ placeholders with the name of our bucket.

```
    "arn:aws:s3:::<bucket-name>/index.html",
    "arn:aws:s3:::<bucket-name>/script.js",
    "arn:aws:s3:::<bucket-name>/style.css"
```

Our updated code should look similar to the following:

```
    "arn:aws:s3:::website-1234/index.html",
    "arn:aws:s3:::website-1234/script.js",
    "arn:aws:s3:::website-1234/style.css"
```

**Note:** Your bucket name will be different. Be sure to use the name of the bucket that you created.

+   Choose **Save changes**
+   Return to the the **Object tab**
+   Select **index.html**.
+   Choose **Delete**.
+   In the **Delete objects** panel, enter `delete` to confirm that you want to remove this file.
+   Choose **Delete objects**
+   Notice that the **index.html** file is listed in the **Failed to delete** pane.

    This confirms that your policy is working and preventing the website’s files from being deleted.

+   Choose **Close** to return to the **Objects** tab.


####    Task 7: Updating the website

Although we have configured a policy to prevent deletion of website files, we can still update the website by editing the HTML file and uploading it to the S3 bucket again.

Amazon S3 is an object storage service, so we must upload the whole file. This action replaces the existing object in your bucket. You cannot edit the contents of an object; instead, you must replace the whole object.

+   On your computer, load the **index.html** file into a text editor (for example, Notepad or TextEdit).

+   Find the text Served from Amazon S3, and replace it with `Created by <YOUR-NAME>` and substitute your name for _<YOUR-NAME>_ (for example, **Created by Sailesh**).

+   Save the file.

+   Return to the Amazon S3 console, and upload the **index.html** file that you just edited.

+   Choose **index.html**, and in the **Actions** menu, choose the **Make public using ACL** option again.

+   Choose **Make public**.

+   Return to the web browser tab with the static website, and refresh the page.

Our name should now be on the page.

Our static website is now accessible on the internet. Because it is hosted on Amazon S3, the website has high availability and can serve high volumes of traffic without using any servers.