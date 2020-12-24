# nginx-proxy-procedure
<br>
Steps:
<br>
Note; this assumes you have the DNS pointing to the PUBLIC IP address.
<br>
Step 1. Create SUBDOMAIN server. with NGINX. Open Port 80, Set an Index.
<br>
Step 2. Go into the LOCAL (192.168.X.X) IP address and Test to See if You see your Index.
<br>

```html
*title* - Your subdomain.com.whatever
<p>hi</p>
```

Step 3. If you Have an Error with step 1 or 2, Start AGAIN.
Step 4. Go into the Main NGINX proxy. Add the Following Conf:
```conf

server {
        listen 80;
        server_name your.domain.com;
        location /{
        proxy_pass "http://192.168.X.X:80";
        proxy_set_header Host $host;
         }
}

```
Step 5. test for Port 80 by going to Domain. If fail, go to step 1.
<br>
Step 6. install Certbot.
<br>
Cert bot can be installed with APT (need PPA), or SNAP.
<br>
Step 7. Run cerbot on PROXY. first. 
<br>
Step 8. Go into your YOUR.DOMAIN.COM server, and run certbot Again.
<br>
step 9, Check for SSL. Set headers where needed.
<br>
Step 10. Write down how to do it, because this wont help alot of People.<br>
