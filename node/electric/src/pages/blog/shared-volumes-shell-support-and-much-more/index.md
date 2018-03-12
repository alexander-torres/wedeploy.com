---
title: "Shared Volumes, Shell Access, and Much More"
description: "We may only be a few months in, but 2018 has been exciting year for us here at WeDeploy. There are many features we've been working on for months and today we finally get to share them all with you."
date: "March 14, 2018"
author: "Zeno Rocha"
image: "/images/blog/post-20--0.jpg"
layout: "blog"
---

<article>

{$page.description}

#### Multiple Shared Volumes

Our volumes feature is a simple way to choose what directory of your service you want to be persistent. This kind of persistent file system is very important for many applications and so that's why we are excited to share that now you can declare multiple volumes in each service and seamlessly share them across all your services.

It's as easy as sharing the volume ID between two services like below.

**Service 1**

```application/json
{
  "id": "service1",
  "volumes": {
    "logs": "foo/app/logs",
    "docs": "bar/documents"
  }
}
```

**Service 2**

```application/json
{
  "id": "service2",
  "volumes": {
    "logs": "foo/app/logs"
  }
}
```

**Read more about multiple shared volumes in our [blog post](/blog/bit-improvements-to-volumes).**

#### Shell Access

Command-line tools are fundamental for developer experience and productivity because they deliver speed, control, traceability, scripting and automation capabilities to the developer’s workflow.

In many cases, it's challenging to get full visibility and control in your service. Shell access makes it easy to see whats going on inside your application, look for side effects that would not be easily spotted in the logs or even call functions like data population or report generation that are just meant to be performed once.

Now WeDeploy Shell provides you with secure, command-line access to your service directly from your browser so you can easily manage your service and perform commands just like you were logged into your server.

**Read more about WeDeploy Shell in our [blog post](/blog/introducing-wedeploy-shell).**

#### One-Click Deploy Button

You heard that right. Now you can embed a button on your website or GitHub repository and give your users one click deployment access to whatever you're building.

In order to accomplish this, you simply link your Git repo in the button. When clicked, it will take you to to the WeDeploy Console and walk you through an interactive process of deployment.

This opens up a world of possibilities to share your projects and services with the world. We can't wait to see what you build.

**See the deploy button in action on one of our [code examples](https://github.com/wedeploy-examples).**

#### CLI Improvements

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Ut odit, vero eaque, ea consectetur repellendus autem itaque doloribus voluptate eius harum! Facilis molestiae illum reprehenderit in fuga, error reiciendis distinctio?

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Libero eius, quos quo consectetur. Quos, molestiae!

Lorem ipsum dolor sit amet, consectetur adipisicing elit. Inventore rerum dignissimos ducimus nihil, deserunt doloremque. Beatae perferendis atque excepturi ipsa, harum, numquam enim voluptas repellendus molestiae veritatis accusantium ut molestias.

#### New Code Examples

Seeing live code is one of the most effective ways to show how a new technology works. Because of this, we feel that it is imperative to keep our code demonstrations well maintained and updated.

To accomplish this, we moved all the boilerplates and demos to a new GitHub Repo called WeDeploy Examples. Our goal is to provide you with more accessible and updated code examples that show how you can easily use WeDeploy. 

We also moved all branches to their own repo. This improved the exposure to the examples with non-web environments like Android, iOS, and React Native.

**Explore our growing number of [code examples](https://github.com/wedeploy-examples).**

#### cURL Documentation

We're always looking for ways to be more accessible to any developer using any kind of programming language.

As you may know, we currently have three official SDKs for [JavaScript](/docs/intro/api-clients/#2), [Swift (iOS)](/docs/intro/api-clients/#3), and [Java (Android)](/docs/intro/api-clients/#4). Those libraries are great and will help you work with our services in a much easier way, but we wanted to go back to the basics and introduce cURL docs.

If you are using languages like PHP, Python, Ruby, Go or C++, this will be a valuable addition to our docs. 

So what are you waiting for? Check out our new [documentation](/docs/) today!

---

Haven't tried WeDeploy before and want to get started? [Create a free account](https://console.wedeploy.com/signup) today and start deploying in seconds!

**If you have any questions, check our [documentation](https://wedeploy.com/docs/) or join our [Slack Community](https://chat.wedeploy.com).**

</article>
