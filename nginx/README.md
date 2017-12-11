This is the playbook to configure the datadog to moniter the nginx server.
1.Run the playbook to install datadog .
2.Run the playbook to configure the nginx

Make sure that: 
 
  We have to Enable the mod_status on your Nginx server, All these changes are made in nginx configuration file itself.
HttpStubStatusModule is the module that does all the metrics, so, you need to know if it is compiled or not. You can check this out using this command:
nginx -V 2>&1 | sed 's,--,n--,g' | grep stub_status
If it is compiled, you should see something like this:
--with-http_stub_status_module 

It is compiled by default on most distributions so, in order to enable Nginx status page the next step is editing nginx.conf. Find your nginx.conf file, it may be at one of this locations.
/usr/local/nagios/etc/nginx.conf
/etc/nginx/nginx.conf
/etc/nginx/sites-enabled/default
Edit the configuration file and add the below block of code.

inside the servers block add below code:

location /nginx_status {
stub_status on;
access_log off;
allow 127.0.0.1;
deny all;
}
