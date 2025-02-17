---
layout: main_guide
title: Rails Girls on Engine Yard
permalink: engineyard
---

# Put Your App Online With Engine Yard

*Created by Mary Jenn, [@mfjenn](https://twitter.com/mfjenn)*

#### Ensure You're Using PostGres for Your Database

You'll need to get your database to work on Engine Yard, which uses a different database than the Rails default. Please change the following in the Gemfile:


		gem 'sqlite3'


to

		group :development do
			gem 'sqlite3'
		end


		group :production do
			gem 'pg'
		end



Run `bundle install --without production` to setup your dependencies.

#### Version Control Systems

You need to add your app to your Git repository. You can do this by running the following in the terminal:


>	`git init`

>	`git add .`

>	`git commit -m "initial commit"`


{% coach %}
This would be a good time to talk about version control systems and git.
{% endcoach %}

### Be Sure to Have a Rails Application in a Repository on Github

You will need to have a GitHub account and a repo we can pull an app from. Follow these directions on [GitHub](https://help.github.com/articles/create-a-repo) to create a repo and push your app to it. If you do not have a working Rails application, you can fork [Engine Yard's sample todo app](https://github.com/engineyard/todo) to your own repo. A coach can walk you through this if you need help.

### Sign up for a Free Trial Engine Yard Account

Go to Engine Yard's [Website](https://www.engineyard.com/) and click on "GET STARTED FREE" to sign up for your Free 500 Hour Trial. The sign up will send you a confirmation email, so go check your email, click on the link and sign in to your account. Click on the link under "Your available applications" that says "Engine Yard Cloud". This will take you to your dashboard.

### Create your Engine Yard Cloud account

1. 	Choose a name for your account. We suggest picking something relevant to who you are, either as a developer, or as an organization if you will be having collaborators. Click the button "Start Trial"

2. 	Feel free to explore what is in the drop downs, but let's go with the defaults for now, since they are in line with a basic Rails app.

3. 	In the box labeled "Git Repository URI", paste the URI from your Github repo. Be sure to use the URI from the SSH version of your application. HINT: The format should be the same as the placeholder text on your Engine Yard application page (or like this: "git@github.com:mfjenn/blogotron.git")


### Putting Your Deploy Key in Place

You should now be on a page that says "Allow Engine Yard access to private repository".

1.	Copy the block of text in the box and go to your GitHub settings page.
2.	Go to the SSH page
3.	Click on the button that says "add a key"
4.	Paste the block of text from your Engine Yard page here. Save it
5.	Go back to your Engine Yard Page and Click the button that says, "My deploy key is in place".

{% coach %}
Talk about the difference between private and public repos and when to use either.
{% endcoach %}

### Creating and Configuring Your Environment

Once you click the "My deploy key is in place" button, you will be taken to a page that says, "Create New Environment for (Your Account Name) App". It is here where we will configure your application. Feel free to explore all the options in the drop downs, but let's use the defaults for now. You do not need to set a domain name.
*	Click the button that says, "Create Environment".

#### Environment Setup

On this page, let's select the staging configuration.
*	Click "Boot This Configuration". You will go to a new page where you see several status bars moving. Our Platform is provisioning your instances. We need to wait till these turn to green dots. This usually takes about 10 minutes, so does anyone need to take a break? It's a good time to go grab some water or a coffee.

{% coach %}
Talk about Staging vs. Production, and why it's important to have replicas. Talk about what is a master & Slave. How does Engine Yard's Failover work? Why is that important?
{% endcoach %}


#### Deploying Your Application

1.	Once all of the lights are green, click "Deploy".
2.	Once you see the phrase "YOUR NAME successfully deployed HEAD" you will know it has been deployed! Congratulations!
3.	Click on the link that says "View your application" to visit your application online.
4.	If you get a red notification that your deploy failed, we just have some debugging to do. Raise your hand and a coach can come over to to help.


#### Stopping Your Instances to Save Your Hours

Once you've got your app up & running, be sure to click the "stop" button to stop the instances so that your don't burn through all of your hours. You can always start them again.

### Additional Resources
*	[A video tutorial](https://support.cloud.engineyard.com/entries/21009937-Video-Tutorial-Set-up-an-Account-and-Deploy-an-Application)

*	[Another Tutorial From the Engine Yard Site](https://support.cloud.engineyard.com/entries/20996751-Tutorial-How-to-Deploy-the-ToDo-Application-on-a-Trial-Account)
