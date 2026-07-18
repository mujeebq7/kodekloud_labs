## Install Nginx and configure HTTPS using a self-signed certificate.

### Description

The system admins team of xFusionCorp Industries needs to deploy a new application on App Server 1 in Stratos Datacenter. They have some pre-requites to get ready that server for application deployment. 

Prepare the server as per requirements shared below: 

1. Install and configure nginx on App Server 1. 

2. On App Server 1 there is a self signed SSL certificate and key present at location /tmp/nautilus.crt and /tmp/nautilus.key. Move them to some appropriate location and deploy the same in Nginx. 

3. Create an index.html file with content Welcome! under Nginx document root. 

4. For final testing try to access the App Server 1 link (via hostname) from jump host using curl command. 
   
   For example: curl -k https://app-server-name/


---

## Prerequisites

- Linux server
- Root access
- SSL certificate
- SSL key

---

### Step 1: SSH into App Server 1
```bash
ssh user@stapp01
```
Become root if required:
```bash
sudo su
```
### Step 2: Install Nginx

```bash
yum install nginx -y
```
### Step 3: Move SSL Certificate and Key
Create a directory for SSL files.
```bash
mkdir -p /etc/nginx/ssl
```
Move the certificate and key.
```bash
mv /tmp/nautilus.crt /etc/nginx/ssl/
mv /tmp/nautilus.key /etc/nginx/ssl/
```
Set secure permissions.
```bash
chmod 600 /etc/nginx/ssl/nautilus.key
chmod 644 /etc/nginx/ssl/nautilus.crt
```
### Step 4: Create the Welcome Page
```bash
echo "Welcome!" > /usr/share/nginx/html/index.html
```
### Step 5: Configure HTTPS
Open the nginx configuration.
```bash
vi /etc/nginx/nginx.conf
```
Add (or modify) the HTTPS server block:
```bash
server {
    listen 443 ssl;
    server_name _;

    ssl_certificate     /etc/nginx/ssl/nautilus.crt;
    ssl_certificate_key /etc/nginx/ssl/nautilus.key;

    location / {
        root /usr/share/nginx/html;
        index index.html;
    }
}
```
### Step 6: Test Nginx Configuration
```bash
nginx -t
```
Expected:
```bash
syntax is ok
test is successful
```
### Step 7: Enable and Start Nginx
```bash
systemctl enable nginx
systemctl restart nginx
```
Verify:
```bash
systemctl status nginx
```
### Step 8: Verify from Jump Host
```bash
curl -Ik https://stapp01
```
