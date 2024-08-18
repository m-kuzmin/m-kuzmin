---
title: Daily Reporter Bot
date: 2023-05-26
github: m-kuzmin/daily-reporter
description: "A solution to a mundane task at my internship"
skills:
  - golang
  - graphql
  - docker
---

## Overview

This was an automation for a mundane task at my internship. I was asked to come up with a telegram bot idea and since I
didn't enjoy collecting all the things I did during the day, I made this project!

The idea is simple:

1. Create and link a GitHub Project
2. Create tasks in that project and at the end of the day they will be naturally end up in the correct tables
3. Run the bot command and get a generated message.

I found that using the bot command in DMs and then forwarding it to the group chat for the internship was way easier and
less anxiety inducing than hoping that you have everything in the right columns first try.

The message template is in the repo [readme](https://github.com/m-kuzmin/daily-reporter?tab=readme-ov-file#daily-reporter)

## Tech stack

- **Golang** to control the bot
- A custom framework that manages the conversation states for each user and interacting with **Telegram API**.
- **Docker**
- **GraphQL** for querying **GitHub API**

## Valuable experience

Don't reinvent the wheel... As a begginer I did that a lot. And it was good because I learned how things worked. But
this project could really have benefited, time-wise, from not having to implement and debug interactions with the
Telegram Bot API. Whenever I considered implementing any new features I was trying to not create more work generating
JSON structs.

That said, I really do like the ideas I used in the implementation, such as the use of Option (inspired by functional
programming). This one thing made figuring out what you got without the endless `dereferenced nil pointer` bugs so much
easier. No longer was a pointer this invisible thing, the types spoke for themselves through the methods they exposed.

If I were to do it again, I would probably do it almost exactly the same way with a few tweaks.

1. I would break out code into separate functions more (to avoid
  [this mess](https://github.com/m-kuzmin/daily-reporter/blob/0c8ccb4394ed9ed456e917e871ed26553e9ba922/internal/clients/telegram/state/root.go#L30C1-L102C1))
2. And I would wrap an existing library and it's pointers instead of writing all the countless JSON structs from
  scratch.

To summarize, while I do have some regrets, the project did solve my problem and provided me with tasks to do during
the internship.
