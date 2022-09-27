---
author: Alo
categories:
- front-end
- testing
date: "2022-09-27"
description: setting up a mock server
tags:
- mock-server
title: Mocking a backend service
draft: true
---

# Mocking a backend service

## Experience
When mocking a backend service, make sure to imitate the real server as close to possible.
Using tools like MSW/data is great, but don't make the mistake to make a RESTful API because it's easier when the server is actually using a different organisation of endpoints.

I have lost a few days trying to remap the real-server to my front-end because I had modelled the mock-server differently than the real server.

Take the time to model your mock server, it will save you a lot of time in the long run.