# Node.js sample app on Appuio!


This example will serve a welcome page.


## Prepare

First create a local project and push it to a git repoitory.

You can use this Node.js sample app from gitlap repoyitory: https://github.com/appuio/example-nodejs

Build project local:

    $ npm install

Run the project local:

    $ npm start


## Creating a project

Create a new project into Appuio. We use the 'oc' command line tool for interact with the Appuio services.

    $ oc new-project example-nodejs --display-name="example-nodejs" --description="Sample Node.js app"

That's it, project has been created.

You can also add permissions to other users:

    $ oc policy add-role-to-user admin rlack -n example-nodejs

Though it would probably be good to set your current project to this (thought new-project does it automatically as well), such as:

        $ oc project nodejs-echo

## Creating new apps

Create a new app into the created Appuio project:

    $ oc new-app https://github.com/appuio/example-nodejs.git -l name=example-nodejs-app

Don't forget to add a route to our created app.

## Success

You should now have a Node.js welcome page.


## Automated build when Code changes with Github-Webhook
The Project must be forked, so you can access the settings in github
In appuio project, Browse -> Builds -> click on Name (example-nodejs) -> Configuration -> copy GitHub webhook URL to clipboard -> Switch to project in Github -> go to Settings -> Webhooks & services -> Add webhook -> paste copied url in Field Payload URL -> Disable SSL Verification -> add Webhook

(https://github.com/appuio/techlab/blob/lab-3.2/labs/09_dockerbuild_webhook.md)


## For more infos

We use the nodejs-ex project (https://github.com/openshift/nodejs-ex) as example.
