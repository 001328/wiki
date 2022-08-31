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


# initialize a new repository

First, create a new repository called *infrastructure*.
> I created it as a public repository so anyone can clone it and deploy my infrastructure to play around with it.

![picture](/assets/images/az-deployments0-0.png)


# clone repository

Now clone the folder to your local computer.

Go to *Code*, then copy the link. Now go to your GitHub Desktop and Add the repository to the root folder - *001328* in my case.

![picture](/assets/images/az-deployments0-01.png)


# set up credentials

The next step is to set up the azure credentials we will need to deploy anything into our azure subscription.
We do this via **GitHub Secrets**.

> Secrets are environment variables that are encrypted. Anyone with collaborator access to this repository can use these secrets for Actions.
> Secrets are not passed to workflows that are triggered by a pull request from a fork. [Learn more](https://docs.github.com/actions/automating-your-workflow-with-github-actions/creating-and-using-encrypted-secrets).

Let's start with adding three secrets.

* subscriptionid
* azurelogincreds
* resourcegroupname

All secrets we use for now are repository secrets. Later on we will add multiple environments and change the secrets to reflect these changes.

To start, go to the Tab **Settings** and then you will find **Secrets** in the Navigation pane on the left. Here, select **Actions**.

![picture](/assets/images/az-deployments0-02.png)


## subscriptionid

First we will start with a subscriptionid.

Open the [azure portal](https://portal.azure.com/) and search for **subscriptions** in the search bar on top.

![picture](/assets/images/az-deployments0-03.png)

From here either select the subscription you want to use or create a new one if it is empty.
Copy the Subscription ID, it should have this format xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.


Switch back to the github tab and add a new repository secret via the button.

![picture](/assets/images/az-deployments0-04.png)

Then add the Subscription ID as the VAlue and give it a name you like.

> I always use lowercaps without hyphens, underscores or other funky stuff as different tools sometimes don't like it and this way I can keep it consistent!
> Also no numbers at the beginning or end
> Here it doesn't matter as GitHub transforms your secret in UPPERCAPS anyways




And you are done!

![picture](/assets/images/az-deployments0-06.png)

> **Please note** that nobody can see this secret again so make sure to save it in your password safe of choice

You can only update the secret, if you do then you have to re-enter it and save again!



## azurelogincreds

The next secret we add are azurelogincreds.

These are the azure login credentials GitHub uses login to azure and create resources.
To do this it uses a [Service Principal](https://docs.microsoft.com/en-us/azure/active-directory/develop/app-objects-and-service-principals) which we will create before.

The azure login credentials have this format:

{
"clientId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
"clientSecret": "xxxxxxxxxxxx",
"subscriptionId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
"tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
}

We already have the subscriptionId and you can find the tenantId by searching for **tenant properties** in the azure search bar (just like you did for the Subscription ID).

![picture](/assets/images/az-deployments0-07.png)

In the properties you can copy the Tenant ID by selecting the little Icon next to the ID.

![picture](/assets/images/az-deployments0-08.png)


Now we only miss the clientId and the clientSecret.

To get them we will go into the active directory and create a new Service Principal.
Then we create a secret for this Service Principal and put the secret value in clientSecret.

> **Note**: Also the secret value will only be shown **once**


## resourcegroupname


next up: set up credentials -> adding 3 secrets: azurelogincreds, resourcegroupname, subscriptionid

{
"clientId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
"clientSecret": "xxxxxxxxxxxx",
"subscriptionId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx",
"tenantId": "xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx"
}




---












Then create 3 Folders: **.github**, **templates** and **templates_custom**. Within **.github** we create another folder **workflows**.
Push all changes to GitHub.

![picture](/assets/images/az-deployments0-99.png)

* The Folder **.github** will contain the yaml files which trigger the actual deployments.
* The Folder **templates** will contain standard templates we can use.
* The Folder **templates_custom** will contain the customized templates


az-deployments0-02.png


Clean up and only leave one single file for creating a resource group.






--

added secret for resourcegroupname_test: "1328_testrg"




---


I kinda like what [this guy](https://github.com/codinfox/codinfox-lanyon/blob/dev/_scss/component/_tag.scss) did.
{% highlight scss %}
{% endhighlight %}




