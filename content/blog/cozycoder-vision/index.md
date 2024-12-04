---
title: "An AI tool designed for developers"
description: ""
summary: ""
date: 2024-11-29T09:00:00Z
lastmod: 2024-11-29T09:00:00Z
draft: false
weight: 50
categories: []
tags: []
contributors: ["Jan Ehrhardt"]
pinned: false
homepage: false
seo:
  title: "" # custom title (optional)
  description: "" # custom description (recommended)
  canonical: "" # custom canonical URL (optional)
  noindex: false # false (default) or true
---

Let's be honest, AI is totally overhyped right now! Especially when it comes to software development, the main driver is efficiency and the hope for making expensive software developers irrelevant in the near future. In my opinion, that's probably not going to happen. Just look at how bad LLMs still are.

But this doesn't mean there is no value in AI for software development. The current LLMs can be really useful for developers.

## What's wrong with AI tools?

Currently, the way how LLMs are used by developers is through a web based chat interface like claude.ai or through some IDE integration like Github Copilot. Some developers are even using IDEs or editors simply because of their promises on AI integration like Coursor.

I also used Github Copilot in VS Code for a while but then I switched Neovim and Copilot became less useful. So I canceled my Copilot subscription and stopped using it. I prefer to use an excellent editor without AI over picking my editor based on its AI capabilities - and in general I don't find AI autocompletion very useful. The main feature of Copilot I used, was the chat. Chat is probably the best way to interact with a LLM today.

But I am not very satisfied with the limited experience of chats. Let's take a simple example:
You are setting up a new project - e.g. a microservice with an API in your enterprise environment. You start by asking Copilot to add a HTTP server and an endpoint. You then ask it for a database connection and some SQL to query the database. You get pretty far with it just by letting Copilot generate all the boilerplate code for you. Finally, you copy the result to files and commit them. 

The next time, you wanna setup a new project, you start from scratch.

But why? Why can't you just fork the previous chat at some point to reuse some parts of the conversation to create another project? Why can't the LLM just take the generated code and create a pull request in your company's Github enterprise installation? Why can't you share the conversation with your colleagues, so they can fork it and reuse it as well?

## Giving Developers more Control

The obvious problem with chat is that everyone is just treating it as chat between a human and a bot. But that's not true. Each time you interact with Copilot, or other LLMs, the full conversation is sent to the LLM as context. There is no reason why this context couldn't be treated like a Git commit history instead.

Let's imagine a tool that gives developers more control and go through the above example:
You start a conversation with a LLM to generate you new project. Of course, it will also run the generated code on your local machine automatically to prove it is working. Once your initial project setup is done, a pull request is provided that can be reviewed by your colleagues. Of course, your colleagues will have access to chat, which is linked in the pull request. Next time one of your colleagues wants to setup another project, they just fork your conversation at some point in the context and continue a new conversation from that point on instead of talking to the LLM from scratch. Since new projects are created frequently in your company, someone is taking your conversation and introduces some parameters to it to use it as a template. Now, you have a reusable conversation as a template that you can simply trigger from your terminal, provide few details (e.g. a project name), and have the code generated.

Of course, not every company creates so many new projects. But this is just one example to show what could be possible, if we were using LLMs more efficiently.

## Designed for your Laptop not the Cloud

The above example gives a rough idea of what you as a software developer should be able to do with Cozy Coder. But in order to make the tool really good - it obviously must run on your laptop!

Many developers use CLIs which can easily be used within scripts to automate tasks. As Cozy Coder is designed for developers, it must provide a proper CLI. But also the access to the file system is important to directly modify local files, if you want to.

Even more important are the constraints of large enterprises. In the last decade, I haven't worked for a single large company here in Europe that did not host their own Github Enterprise or Gitlab or similar tool. The code is capitalized and must to be kept secret. Hosting the code on a self-hosted Github Enterprise that is only accessible from your VPN is how you achieve this. So why should one of those companies start sending code to some LLM hosted in the cloud? Everything that runs locally on your laptop is significantly easier to use within larger enterprises.

Cozy Coder will of course not be limited to local LLMs but they will always be the preferred choice and well supported. Ideally, we will all together achieve the usage of local LLMs, where possible and only use the cloud based ones, where necessary.

Of course, Cozy Coder will also have a server side part. But it will be mainly for enabling sharing and collaboration as well backups of data.

## Commercial Open Source

Cozy Coder is an open source project, and I wouldn't develop it if it wasn't. But with the end of zero interest rate policy, sponsoring as a strategy to fund an open source project has become more difficult.

That's why the goal is to have a more sustainable financing strategy by building a for-profit business on top of the open source project. This will be achieved by following the open core approach. While Cozy Coder itself will be available under Apache-2.0 license and can be used for free, the server side code will be licensed under a Polyform non-commercial license. Thus, it still allows personal or educational use and even code modification, the commercial use requires a paid license.

## Follow the development

I am just starting with the development now and if you are interested in the project, feel free to follow its progress or even contribute to it. Here are some options:

- Youtube
- Bluesky
- Discord
