---
layout: post
title:  "Azure Deployment 0 // Repository setup"
date:   2022-08-29 01:10:00 -0400
tags: azure-deployments
---

In this series **azure-deployments** we will deploy our infrastructure to azure.
The first step is to understand how a deployment works in general so we have a base to build upon.

I use github actions as it is pretty powerful and simple.

> **Important**: If you use enterprise github you need a self-hosted runner which needs to be installed on a VM
> github.com does not need this


# set up repository

First, create a new repository called *infrastructure*.
> I created it as a public repository so anyone can clone it and deploy my infrastructure to play around with it.

![picture](/assets/images/az-deployments0-0.png)

Then create 3 Folders: **.github**, **templates** and **templates_custom**. Within **.github** we create another folder **workflows**

* The Folder **.github** will contain the yaml files which trigger the actual deployments.
* The Folder **templates** will contain standard templates we can use.
* The Folder **templates_custom** will contain the customized templates





Clean up and only leave one single file for creating a resource group.




# set up credentials

* azurelogincreds
* resourcegroupname
* subscriptionid

next up: set up credentials -> adding 3 secrets: azurelogincreds, resourcegroupname, subscriptionid

{

"clientId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",

"clientSecret": "xxxxxxxxxxxx",

"subscriptionId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",

"tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"

}

--

added secret for resourcegroupname_test: "1328_testrg"




---


I kinda like what [this guy](https://github.com/codinfox/codinfox-lanyon/blob/dev/_scss/component/_tag.scss) did.
{% highlight scss %}
{% endhighlight %}




