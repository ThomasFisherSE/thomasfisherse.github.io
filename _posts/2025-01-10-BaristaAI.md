---
layout: post
published: true
title: BaristaAI
subtitle: An AI assistant to help with coffee brewing.
date: 2025/01/10
thumbnail-img: "/assets/img/projects/baristaai/AICoffeeAssistantGenerated.png"
cover-img: ["/assets/img/projects/baristaai/BaristaAI-TooBitterPrompt.png"]
---

## Introduction
BaristaAI is a personal project I worked on after buying an espresso machine and wanting to improve the coffee I was making.

There are many variables that can have an impact on the quality of an espresso. The taste of an espresso can help give some hints as to what may need tweaking to get the best you can out of your coffee. 

I created BaristaAI as a simple but all-encompassing assistant app to help with coffee brewing. It works using a large language model (LLM) which has been provided some initial context to help guide conversations to give useful tips on coffee brewing.

## Example

If your espresso tastes a bit too bitter:

![BaristaAI: Too Bitter Prompt](/assets/img/projects/baristaai/BaristaAI-TooBitterPrompt.png)

BaristaAI responds with some helpful tips (and follow up questions if necessary) to reduce the bitterness of the espresso next time you make it.

![BaristaAI: Too Bitter Response](/assets/img/projects/baristaai/BaristaAI-TooBitterResponse.png)

## Some Technical Details

- BaristaAI is built with .NET MAUI (currently targetting .NET 8), and can be deployed for Android, iOS, or Windows Desktop
- Powered by Google Gemini (configured to use the `gemini-1.5-pro` model by default) via the [`generative-ai` package for .NET](https://github.com/mscraftsman/generative-ai)
- Abstracted LLM service, making it easy to swap out the implementation that uses Google Gemini with other LLM APIs (e.g. OpenAI) in the future
- Uses dependency injection (DI)
- Follows MVVM design pattern