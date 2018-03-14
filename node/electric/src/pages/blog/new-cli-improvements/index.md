---
title: "New CLI Improvements"
description: "We have some exciting CLI improvements to share with you, as well as a look into the future of our interface."
date: "Mar 12, 2018"
author: "Henrique Vicente"
image: "/images/blog/post-1--0.png"
layout: "blog"
---

<article>

{$page.description}

#### Smarter

In the past we have required many flags like `--project` or `--service` to make actions on our CLI work. Now we are introducing a smarter, more interactive way of performing your tasks from your terminal.

Before, in order do things like `scale` you would need to pass this whole command:

```
we scale --project notebook --service notes 4
```

Now you can simply enter `we scale 4` and an interactive process will begin where you can declare your project and service.

_INSERT ANIMATION HERE_

This powerful feature is available for pretty all the available commands. So what are you waiting for? Go to your command line, type something like `we env` or `we domain` and sip on a cold beer as we prompt you through the rest of the process. 

#### Better

We have big ambitions for what we want our command-line interface to provide to developers like you.

**we new**

Many of the features that are currently available on the web console, like creating new services and projects, is not yet on the CLI. Well, not until today! 

That's right, now you can simply run `we new` to create a new project and even start installing new services right from the comfort of your terminal.

_INSERT ANIMATION HERE_

Like the others, the `we new` command provides the beautiful new step-by-step user experience. You don't need to memorize any flags or even the IDs of your project. Just type `we new` and we will walk you through the rest.

**we curl**

Besides our most popular commands, we have a few hidden ones for those who want to do some serious work. One of those secret commands is `we curl`.

With it, you can use any [curl](https://curl.haxx.se/) parameters to write requests seamlessly to the server. However, you don't have to include the full API host when making requests (e.g. `we curl /projects`).

_INSERT ANIMATION HERE_

There are other little tricks and hidden features in our CLI. If you want to see more, just run `we -H` to explore.

#### Future

The future is very important to us. We cannot sacrifice our quality in a desire for rapid development. It is important that both are married so we can deliver you the highest quality software in the most timely manner.

With that said, we wanted to share with you a few things we have planned and how we are working towards raising the bar in developer experience.

**New Commands**

Many of our users have requested the ability to access their containers in a Linux shell. To do this, we are working on the `we exec` and `we ssh` commands.

These will open up many doors of opportunity to do things like debug and automate applications, migrate data and setup customized continuous integration.

We are also excited to announce that the WeDeploy Shell feature is live in our web console. If you want to know more about it, read our [WeDeploy Shell Blog Post](/blog/introducing-wedeploy-shell/).

**Installation**

Installing the WeDeploy CLI is a step we don't take lightly. We've come a long way since the beginning, but we have plans to help make this part of getting started even easier for Windows and macOS users.

**Functional Tests**

Each line of code and vendor dependencies used to generate the `we` binary is audited by the CLI team. Our application code is also unit tested and verified against defects with code quality and static analysis tools. 

It is important to us that we release safely and securely. Because of this, we are currently adding automated functional tests to our quality assurance process.

This has actually been in the works for a while now. After trying to write our own tests in Go and attempting to maintain our own library, we decided to use an awesome project called [expect](http://core.tcl.tk/expect/index). It is the same automating testing tool that Git uses and has all the functionality we were looking for. 

We are very excited about the future of CLI testing and overall release quality.

**Updates**

Currently, when you run `we update` we just install the newest changes to the CLI. Soon we will show you a list of changes when you run this command.

We hope you are as excited as we are about the new WeDeploy CLI development. If you have any ideas or questions that you would like to share with us, feel free to **[join our community](https://chat.wedeploy.com/)** or **[follow us on Twitter](https://twitter.com/wedeploy)**.

</article>
