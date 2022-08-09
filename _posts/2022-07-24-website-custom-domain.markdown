---
layout: post
title:  "A custom name for your GitHub pages website"
date:   2022-07-24 01:05:00 -0400
categories: website
tags: jekyll github-pages
---

Now we want to give our new website a cool looking name.

The product I am building is called the azure data platform, so I want to use [azuredataplatform.net](https:azuredataplatform.net)


> Steps:
> 1. Find a great domain and buy it
> 1. Point the domain to GitHub
> 1. add the domain to GitHub


# Step 1: Find a great domain and buy it
There are tons of locations where you can buy a domain.
One of the biggest is [GoDaddy](https://www.godaddy.com), I prefer [Google Domains](https://domains.google.com) because their prices appear to be more stable to me. 

![domain1](/assets/images/website_domain1.png)

Once you bought it it will appear under **My domains** and you can go to the properties with the **Manage** Button
![domain2](/assets/images/website_domain2.png)

> I will use my own site *azuredataplatform.net*

# Step 2: Point the domain to GitHub

In the *Manage* Settings you will find *DNS*
![domain3](/assets/images/website_domain3.png)

From here we need to point the new domain to GitHub
To do so, please add 2 custom records:
    1. Type A record
    1. Type CNAME record

The Type a record needs to point to GitHubs IP-Addresses. Do not put anything in the field "Host name".
Enter the following records into the field "Data" (add more with the +)
  * 185.199.108.153
  * 185.199.109.153
  * 185.199.110.153
  * 185.199.111.153

The Type CNAME record needs to point to your GitHub repository. Please create a new record and enter **www** in the field "Host name". 
Enter the following record into the field "Data".
  * 001328.github.io

Then hit *Save*
![domain4](/assets/images/website_domain4.png)


# Step 3: add the domain to GitHub

Now go to your github repository, open the settings for **Pages** and enter your newly created domain into the field for **Custom domain** and Save

It will check the DNS records you just made and once successful publish your new website.
![domain5](/assets/images/website_domain5.png)

Once the DNS check is successful your website is published with your new name!
Please be aware that GitHub needs to provision a TLS certificate to ensure it's secure.
![domain6](/assets/images/website_domain6.png)


Once the certificate is provisioned, select the option **Enforce HTTPS**
![domain7](/assets/images/website_domain7.png)

> Attention: It can take an hour until your website works properly

# Step 4: Fix CSS

When you change your domain name your website will probably look like this
![domain8](/assets/images/website_domain8.png)

To fix it just adjust the baseurl and url in your local config file, then push the changes to github
![domain9](/assets/images/website_domain9.png)

> remember to wait 1 Minute so the CSS can load

The final result:
![domain10](/assets/images/website_domain10.png)

# The End

> This Tutorial follows the offical [Github Docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site) with a littlle help from [this guy](https://hossainkhan.medium.com/using-custom-domain-for-github-pages-86b303d3918a)


> By the way - DNS means **Domain Name Service**