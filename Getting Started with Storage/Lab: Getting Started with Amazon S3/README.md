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
This lab requires approximately **30 minutes** to complete. You will have a total time of **180 minutes** to complete this lab.

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

    An S3 bucket name is globally unique, and all AWS accounts share the namespace. After you create a bucket, no other AWS accounts in any AWS Regions can use the name of that bucket unless you delete the bucket.

    For this lab, we use a bucket name that includes a random number, such as **website-123**.

+   For **Bucket name**, enter `website-<123>` and replace _<123>_ with a random number.

    Public access to buckets is blocked by default. Because the files in your static website will need to be accessible through the internet, you must permit public access.

+   For **Object Ownership**, choose **ACLs enabled**.

+   Choose **Bucket owner preferred**.

+   For **Block Public Access settings for this bucket**, clear the check box for **Block _all_ public access**, and then select the box that states **I acknowledge that the current settings might result in this bucket and the objects within becoming public**.

+   For **Bucket Versioning**, choose **Enable**.

    >Note: Once you turn on (enable) bucket versioning, you can’t turn it off.

+   For **Tags**, choose **Add tag**, and enter the following:

    +   **Key:** `Department`
    +   **Value:** `Marketing` You can use tags to add additional information to a bucket, such as a project code, cost center, or owner.

+   Choose **Create bucket**

+   In the **Buckets** section, choose the name of your new bucket.

+   Choose the **Properties** tab.


####    Task 2: Configuring a static website on Amazon S3
You will now configure the bucket for static website hosting.

+   Scroll to the **Static website hosting** panel.
+   Choose **Edit**

+   Configure the following settings:

    +   **Static web hosting:** Choose **Enable**.
    +   **Hosting type:** Choose **Host a static website**.
    +   **Index document:** Enter `index.html`
    +   **Error document:** Enter **error.html** 
    **Note:** You must enter `index.html` and `error.html` even though they are already displayed.

+   Choose **Save changes**

+   In the **Static website hosting** panel under **Bucket website endpoint**, choose the link.

    You receive a _403 Forbidden_ message because you have not yet configured the bucket permissions. Keep this tab open in your web browser so that you can return to it later.

    You have configured your bucket to host a static website.


####    Task 3: Uploading content to your bucket

In this task, you upload the static files to your bucket.

+   Choose (right-click) each of the following links, and download the files to your computer:

    Ensure that each file keeps the same file name, including the extension.

    +   <a href="./src/index.html" target="_blank">index.html</a>
    +   <a href="./src/script.js" target="_blank">script.js</a>
    +   <a href="./src/style.css" target="_blank">style.css</a>

+   Return to the Amazon S3 console, and choose the **Objects** tab.
+   Choose **Upload**
+   Choose **Add files**
+   Choose the three files that we downloaded.
+   Choose **Upload**

Your files are uploaded to the bucket.

+   Choose **Close**


####    Task 4: Turning on public access to the objects
