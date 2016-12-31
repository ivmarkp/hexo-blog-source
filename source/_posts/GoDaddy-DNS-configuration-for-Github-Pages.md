---
title: GoDaddy DNS Configuration for Github Pages
date: 2016-Sep-12
tags: 
	- GoDaddy
	- Github Pages
---
If you've also registered your domain name through GoDaddy and wondering how to setup a custom domain for your Github-Pages-hosted website or blog then read on for few quick steps to do exactly that.

1. Create a file named "CNAME" in the root directory of your website's repository.

2. Open CNAME and type in the domain in it. E.g. vivekpal.me

3. Now add and commit the changes just made:
````
	$ git add ./CNAME && git commit -m "Add custom domain"
	$ git push origin [branch name]
```
4. Login to your GoDaddy account and go to "Manage DNS" of your domain.

5. Under "Records" section, click on "Add" to add new record.

6. First, setup an apex domain with the following credentials:
  * **Type** -- A
  * **Name** for the record E.g. "@".
  * **Points to** -- 192.30.252.153 or 192.30.252.154
  * **TTL** -- Set it to automatically selected default value.

7. Add another record for a www subdomain with the following credentials:
  * **Type** -- CNAME
  * **Name** -- www
  * **Points to** -- username.github.io
  * **TTL** - Default again.

8. Save the records and wait for a few minutes for DNS settins to propagate.

> If you found something wrong that needs correction, please let me know.

**References**
- [Setting up an apex domain and www subdomain](https://help.github.com/articles/setting-up-an-apex-domain-and-www-subdomain/)
- [Domains Help -- Manage DNS](https://in.godaddy.com/help/manage-dns-680)
