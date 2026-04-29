FULL COMMAND FLOW (LINUX – EC2
STATIC WEBSITE)
STEP 1: Connect to EC2
chmod 400 mykey.pem
ssh -i mykey.pem ec2-user@<public-ip>
STEP 2: Update System
sudo yum update -y
STEP 3: Install Apache + Git
sudo yum install httpd git -y
STEP 4: Start & Enable Apache
sudo systemctl start httpd
sudo systemctl enable httpd
STEP 5: Clone Your GitHub Repo
cd /home/ec2-user
git clone https://github.com/AnantGalande/STATIC.git
STEP 6: Move Files to Web Directory
sudo rm -rf /var/www/html/*
sudo cp -r STATIC/* /var/www/html/
STEP 7: Set Permissions
sudo chmod -R 755 /var/www/html
STEP 8: Restart Apache
sudo systemctl restart httpd
STEP 9: Access Website
Open in browser:
http://<public-ip>
