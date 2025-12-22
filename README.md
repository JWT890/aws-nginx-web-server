# aws-nginx-web-server

When learning AWS, its important to showcase knowledge or skill in AWS by setting up simple projects to showcase knowledge such as a Nginx web server. Showcases knowledge in S3 buckets and networking, especially when deploying from a Linux server.   
After getting a Linux VM Setup, set its network to Bridged.   
First install nginx by typing sudo apt install nginx -y, then sudo systemctl start nginx and then sudo systemctl enable nginx.  
Then paste http:localhost in the Linux VM and you will see the default nginx information:  
<img width="809" height="812" alt="image" src="https://github.com/user-attachments/assets/2d8a8f31-2c45-4307-97be-66fd8bdfc9bf" />  
Next go to S3 and create a bucket named something like for the nginx bucket. Then go the IAM center and create a user the AmazonS3FullAccess policy on it, click on create access keys, set the description to Kali VM Nginx S3 Project, save the keys somewhere and click on done.  
Then go the Linux VM and enter the command sudo apt install awscli -y  
Then type aws configure and type in your access key, secret key, region, and ouput format as json then type sudo mkdir -p /var/www/s3-project, then type sudo chown -R $USER /var/www/s3-project  
Enter in something like this:  
<img width="718" height="438" alt="image" src="https://github.com/user-attachments/assets/e6b77542-ab28-403e-8b03-8eaa7de0c052" />  
And save it.  

