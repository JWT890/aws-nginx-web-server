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
Then type echo "Hello from S3" > /tmp/test-file.txt, then type aws s3 cp /tmp/test-file.txt s3://nginxbucket10.  
Then type aws s3 ls s3://nginxbucket10/ to verify its in the there:  
<img width="389" height="38" alt="image" src="https://github.com/user-attachments/assets/ee879882-d306-406c-affa-b31ac3abd509" />  
<img width="1515" height="97" alt="image" src="https://github.com/user-attachments/assets/62cf4ef7-4098-46da-9eed-8df8ac1ee3ec" />  
Next its time to configure Nginx, type sudo nano /etc/nginx/sites-available/s3-project and enter in this configuration:  
<img width="374" height="305" alt="image" src="https://github.com/user-attachments/assets/08c17d04-9ea4-48cd-b0ac-981d970ab30d" />    
Then type ~/s3-sync.sh to write a script
And write:  
<img width="350" height="186" alt="image" src="https://github.com/user-attachments/assets/4fcabffd-69ca-46d6-be01-0c06e309ac6e" />  
Then save it and type chmod +x ~/s3-sync.sh and then ./s3-sync.sh


