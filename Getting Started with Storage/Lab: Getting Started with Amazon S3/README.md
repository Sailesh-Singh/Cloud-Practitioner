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