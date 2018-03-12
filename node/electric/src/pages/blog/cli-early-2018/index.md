---
title: "state of we, early 2018"
description: "What have we accomplished on the CLI during the first quarter? What is coming next?"
date: "Mar 12, 2018"
author: "Henrique Vicente"
image: "/images/blog/post-1--0.png"
layout: "blog"
---

<article>

{$page.description}

Hi,

On this blog post, I (or should I say we?) am going to talk a little bit about the WeDeploy Command-Line Interface tool, "we".

## Forget about --project or --service?
We don't require them anymore. Instead, you might use the commands interactively. What commands? Most commands. In doubt, just try and it should work.

For example, instead of doing `we scale --project notebook --service notes 4` you can just try `we scale 4` and select the service you want to scale.

ASCIINEMA ANIMATION: some commands, running fast

## we scale, we env, we domain
Oh, yes. Now we have a command to scale how many instances you want to run for each service.
Also, the `we env` and `we domain` commands are now — finally! — very user-friendly!

ASCIINEMA ANIMATION: we scale, we env, and we domain (one after the other)

## we new, we open commands
With `we new` you can finally create projects and services from the CLI without having to do a deployment of a directory.

ASCIINEMA ANIMATION: we new project, then we new service

To be fair, no matter how lazy you might be feeling after a long day of work you're probably never using `we open`, except if you are using the CLI programmatically. Then it might be awesome!

SMALL GIF: we open to open browser

## "we curl", for when things get serious
Here's a little secret. When you use `--help` you don't see all commands and flags we support. Use `-H` instead to see them. Some of them are useful for debugging, provides internal support for other commands or features, or both.

One of the hidden commands is `we curl`. With it, you can do write requests to the server in an easier way (using your authenticated credentials) than using curl stand-alone. In special, this command pipes stdin, stderr, and stdout transparently, and accepts any [curl](https://curl.haxx.se) parameters. You can spare writing the full host to the API service though. Like this: `we curl /projects`.

ASCIINEMA ANIMATION: we curl /projects

## Integration tests

## What is coming next?
### New commands! `we exec` and `we ssh` are coming.
Both are quite similar: they allow you to run commands or access an instance of your containers, allowing you to debug or automate your applications, migration processes, or Continuous Integration task.

They should be out soon on the CLI. Fortunately, we were able to have them faster on the [console](https://console.wedeploy.com), and you can take a sneak peek there already! Advantages for the version that will be available on the CLI includes piping stdin, stderr, and stdout, and exit codes.

ASCIINEMA ANIMATION: functional tests running

### Update notices
Get to know the changes after you run `we update` without to read, well… A blog post.

### Installer for Windows and macOS.
Installing on Windows might feel scary sometimes (if using the installer) and we should fix this within this quarter. For macOS, the situation is way better. But there's still room for improvements.

### Integrating of our functional tests with our build and distribution service
Each line of code (including vendor dependencies) used to generate the `we` binary is audited by the CLI team.

Our application code is unit tested and verified against defects with code quality and static analysis tools. We do "we" releases (pun intended) safely and securely.

However, even though we care about our CLI software development, one essential thing was still missing from our setup. And it was functional testing.

The initial approach to writing functional testing was using Go itself to write it. We wrote a [small library](https://github.com/henvic/pseudoterm) to handle the CLI testing with Go. However, things weren't moving so quickly, then we moved to [cucumber aruba](https://github.com/cucumber/aruba) and faced some limitations, and we were left lagging behind without a proper solution.

One day, we found the [goexpect](https://github.com/google/goexpect) project and our first reaction was "look, Google did a library similar to ours! Yups! One less thing to maintain! Let's check it out!".

We found out we were lagging for 26 years. goexpect is named after [expect](http://core.tcl.tk/expect/index), a traditional Unix tool from the 90s.

The Testing team gave it a try, and it fitted perfectly. It turns out it is a robust framework for automating CLI programs originally developed for Unix systems. git, ssh, passwd, and many other interactive programs rely on it for functional testing.

It is a significant advance for our team because prior to that the closest we had were integration tests that checked that the CLI tool was working fine with mocks. Even one or other essential commands such `we deploy`, were left without automated functional testing, demanding costly and error-prone manual testing at each release.

## Summary
With this, we conclude what we *expect* to have on the CLI within the following three months.

We hope you enjoyed to know more about the WeDeploy CLI development. If you have any ideas that you would like to share with us, feel free to [contact us](https://chat.wedeploy.com/).

</article>
