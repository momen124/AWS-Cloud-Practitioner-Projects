# Hosting a Static Website on Amazon S3

## Objective
Host a static website on Amazon S3 by creating a bucket, uploading HTML and image files, enabling static website hosting, and making files publicly accessible to learn cloud storage and website hosting.

## Steps
1. **Created S3 Bucket**:
   - Created a bucket named `nextwork-website-project-momen` in the `us-east-1` region for low latency.
   - Enabled ACLs with **Bucket owner preferred** and turned on bucket versioning.
   - Disabled **Block all public access** and acknowledged the warning to allow public access.
   - Screenshot: [bucket-creation.png](screenshots/bucket-creation.png)

2. **Uploaded Website Content**:
   - Downloaded `index.html` and `NextWork - Everyone...love_files.zip`.
   - Unzipped the `.zip` file to extract the image folder.
   - Uploaded `index.html` and the `NextWork - Everyone...love_files` folder (44 image assets) to the bucket.
   - Screenshot: [objects-uploaded.png](screenshots/objects-uploaded.png)

3. **Configured Static Website Hosting**:
   - Enabled static website hosting in the bucket’s **Properties** tab.
   - Set **Hosting type** to **Host a static website** and **Index document** to `index.html`.
   - Copied the bucket website endpoint URL and encountered a 403 Forbidden error (expected due to private objects).
   - Screenshots: [static-website-setup.png](screenshots/static-website-setup.png), [403-error.png](screenshots/403-error.png)

4. **Made Objects Public**:
   - Selected `index.html` and the image folder in the **Objects** tab.
   - Used **Actions > Make public using ACL** to grant public read access.
   - Refreshed the endpoint URL to successfully display the NextWork website.
   - Screenshot: [website-success.png](screenshots/website-success.png)

5. **Secret Mission - Bucket Policy**:
   - Added a bucket policy to deny deletion of `index.html`:
     ```json
     {
       "Version": "2012-10-17",
       "Statement": [
         {
           "Effect": "Deny",
           "Principal": "*",
           "Action": "s3:DeleteObject",
           "Resource": "arn:aws:s3:::nextwork-website-project-momen/index.html"
         }
       ]
     }