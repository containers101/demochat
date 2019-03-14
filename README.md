Build status: [![Codefresh build status]( https://g.codefresh.io/api/badges/build?repoOwner=containers101&repoName=demochat&branch=master&pipelineName=demochatdfdf&accountName=Razielt77_github&type=cf-1)]( https://g.codefresh.io/repositories/containers101/demochat/builds?filter=trigger:build;branch:master;service:58543cb490a3f40100db408f~demochatdfdf)
Demo for Axway
![Let's Chat Greylock](http://i.imgur.com/0a3l5VF.png)
![Screenshot](http://i.imgur.com/C4uMD67.png)
A self-hosted chat app for small teams or big Gal by [Security Compass][seccom].

For commit

## Features and Stuff

* BYOS (bring your own server)
* Persistent messages
* Multiple rooms
* Private and password-protected rooms
* New message alerts / notifications
* Mentions (hey @you/@all)
* Image embeds / Giphy search
* Code pasting
* File uploads (Local / [Amazon S3][s3] / [Azure][azure])
* Transcripts / Chat History (with search)
* XMPP Multi-user chat (MUC)
* 1-to-1 chat between XMPP users
* Local / [Kerberos][kerberos] / [LDAP][ldap] authentication
* [Hubot Adapter][hubot]
* REST-like API
* Basic i18n support
* MIT Licensed


## Deployment 

For installation instructions, please use the following links:

* [Local installation][install-local]
* [Docker][install-docker]
* [Heroku][install-heroku]
* [Vagrant][install-vagrant]

## Support & Problems

We have a [troubleshooting document][troubleshooting], otherwise please use our
[mailing list][mailing-list] for support issues and questions.


## Bugs and feature requests

Have a bug or a feature request? Please first read the [issue
guidelines][contributing] and search for existing and closed issues. If your
problem or idea is not addressed yet, [please open a new issue][new-issue].


## Documentation

Let's Chat documentation is hosted in the [wiki]. If there is an inaccuracy in
the documentation, [please open a new issue][new-issue].


## Contributing

Please read through our [contributing guidelines][contributing]. Included are
directions for opening issues, coding standards, and notes on development.

Editor preferences are available in the [editor config][editorconfig] for easy
use in common text editors. Read more and download plugins at
<http://editorconfig.org>.


## License

Released under [the MIT license][license].


[wiki]: https://github.com/sdelements/lets-chat/wiki
[troubleshooting]: https://github.com/sdelements/lets-chat/blob/master/TROUBLESHOOTING.md
[mailing-list]: https://groups.google.com/forum/#!forum/lets-chat-app
[tracker]: https://github.com/sdelements/lets-chat/issues
[contributing]: https://github.com/sdelements/lets-chat/blob/master/CONTRIBUTING.md
[new-issue]: https://github.com/sdelements/lets-chat/issues/new
[editorconfig]: https://github.com/sdelements/lets-chat/blob/master/.editorconfig
[license]: https://github.com/sdelements/lets-chat/blob/master/LICENSE
[ldap]: https://github.com/sdelements/lets-chat-ldap
[kerberos]: https://github.com/sdelements/lets-chat-kerberos
[s3]: https://github.com/sdelements/lets-chat-s3
[seccom]: http://securitycompass.com/
[hubot]: https://github.com/sdelements/hubot-lets-chat
[azure]: https://github.com/maximilian-krauss/lets-chat-azure
[install-local]: https://github.com/sdelements/lets-chat/wiki/Installation
[install-docker]: https://registry.hub.docker.com/u/sdelements/lets-chat/
[install-heroku]: https://github.com/sdelements/lets-chat/wiki/Heroku
[install-vagrant]: https://github.com/sdelements/lets-chat/wiki/Vagrant


 


![Let's Chat Greylock](https://codefresh.io/wp-content/uploads/2017/03/lets-chat.png)


Use this tutorial to familiarize yourself with codefresh.yml file and Codefresh functionality.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/11.png)


This tutorial is based on Let’s Chat [app].

https://github.com/containers101/demochat

### Let’s Chat is self-hosted chat app for small teams or big

This tutorial will walk you through the process of adding the following :


* Build step - that will build Docker image for your Let’s Chat app

* Push to registry step - that will push your image to Docker Hub

* Unit Test step - A freestyle step that runs the unit test of the demo chat after the build 

* Composition step - This step will create and launch a composition.

So, the first thing you need to do is :

## Fork our repo  

Enter the following link and fork Let’s Chat app!: ```https://github.com/containers101/demochat```


## Add a service
Now enter Codefresh and add your Let’s Chat app as a Codefresh service.

Click on ___Add Repository___

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/add-repo.png)


Now add your forked demochat repo. You can search for it by typing "demochat" to search. You can also Add by URL here.

Also, choose the branch for your first build (in this case ```master```)

When you finish press ___Next___.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/select-repo2.png)


Select how you would like to setup your repository. In this case, our repo has a ___Dockerfile___, so we'll select the middle option. 


![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/15.png)

By default, Codefresh searches for your Dockerfile at the root level of your repository, by the name "Dockerfile". The demo-chat example includes a Dockerfile in the root level.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/16.png)


Review your Dockerfile, and click ___Create___ to add your repository.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/17.png)

Clicking on ___Build___  button will trigger a regular build.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/18.png)

Great, you  are running  your build for the first time!

## Push your image to Docker registry
In Codefresh the build images will be automatically pushed to Codefresh registry and there’s no need to specify the [Codefresh Docker Registry](https://docs.codefresh.io/v1.0/docs/codefresh-registry)  for the block __Push to Docker Registry__ in the pipeline of repository and you can just skip this step.

Click on ___Repositories___, and then click on the ___Pipelines___ gear.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/19.png)

Scroll down to ___Workflow___, and you will see a ___Push to Docker___ button. If you have set up your credentials, click ___Save___ at the bottom of the screen. Otherwise- click on the ___integration page___ link.

Write your User/Password info, and click ___Save___ to connect.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/20.png)


## Unit test your image
Let's head over to ___Piplines___ again.
![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/19.png)

Scroll down to Workflow under ___Build and Unit Test___

We'll type in ```echo $(date)``` in the Unit Test Script area. This will print the date, and we'll be able to see our test in action.

Let's click ___Save___, and ___Build___ to see it in action.

Great- the date has been printed!

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/22.png)
 
 
Now let's add a full composition that also contains mongo db.


## Add composition

Our Let's Chat app needs mongo in order to work, so let's add it!

You can read more about compositions in our docs, but we will also walk through the process here :
https://docs.codefresh.io/docs/create-composition


Click the ___Composition___ view icon in the left pane, and click the ___Add Composition___.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/1.png)

Choose a name for your composition

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/2.png)

We are going to build our comp from scrath, so click ___Empty Composition___

![Screenshot](https://codefresh.io/wp-content/uploads/2017/04/empty_comp.png)

Now we will click ___Add Service___ and add demochat, the port (50000), and mongo.
Everything looks good here- so let's go ahead and launch by clicking the rocket ship...

![Screenshot](https://codefresh.io/wp-content/uploads/2017/04/savelaunch_final.png)


Once it has completed, a link to our app will be displayed. Let's click it to see if it worked.


![Screenshot](https://codefresh.io/wp-content/uploads/2017/04/completed_in.png)

Success! We have successfully launched a composition.

![Screenshot](https://codefresh.io/wp-content/uploads/2017/03/10.png)






[app]: https://github.com/containers101/demochat

## About Containers 101

[Containers 101](https://www.meetup.com/Containers-101-meetup/) is online/offline meetup group based in Mountain View that provides guides and helps developers work with Containers. Created by [Codefresh](https://codefresh.io/) which provides environments for every commit, Docker CI and CD, and an embedded registry. 

[Join Containers 101](https://www.meetup.com/Containers-101-meetup/)
Learn more about [Codefresh](https://codefresh.io/)


