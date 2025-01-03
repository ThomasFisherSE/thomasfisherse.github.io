---
layout: post
published: true
title: Activity Planner Desktop App (WPF) - Work In Progress
subtitle: A Windows desktop application built using WPF providing activity planning capabilities.
date: 2024/12/10
thumbnail-img: "/assets/img/projects/activityplanner/AssignActivityTimeSlot.png"
---

## Motivations
### Planning Disney
One of the biggest shared interests between myself and my wife Ffion is our love of Disney. Specifically, the theme parks like those at Walt Disney World in Florida, where there are 4 separate Disney theme parks. We both enjoyed the theme parks with our families when we were younger, but have carried it into our adult life too, choosing Disney World as our main holiday destination most times we take a trip.

As anyone familiar with going to Disney parks in the last few years can attest to, it's no simple trip! There are all sorts of aspects of the holiday to consider:
- Restaurant reservations
- Park reservations
- "Fastpass" reservations for reduced waiting times
- Timed or even dated events / activities / shows
- Dining & drinks packages
- A lot more, but I'll stop here since this isn't a Disney parks blog (yep Disney parks blogs exist by the thousands, because there's so much involved now!)

This brings me to another thing my wife and I have in common: Our need to plan. We're not ones to rock up and see where the day takes us. No, we need an carefully thought out itinerary, planned with both enjoyment and efficiency in mind, because efficiency **is** enjoyment! To us at least. 

#### The Mega Spreadsheet
Whenever we plan a Disney parks trip, we usually set up a huge spreadsheet detailing what we plan to be doing each day. It would have colour coded locations such as which park a particular activity would take place in. We'd add icons as notation for various attributes like "this restaurant needs a reservation", or "this restaurant is available on the Disney dining plan". We also use the spreadsheet for some analysis ourselves, like counting how many hours we are spending at each park to determine whether we're spending enough time at each park.

This could be quite a time consuming task, and doesn't look that great in the end as a spreadsheet - it's not really what spreadsheet applications are designed for.

### Expanding my Skills

I'm always keen to hone my skills in different tools and technologies. Something I've had some brief experience with for internal projects at work, but that I wanted to explore further is WPF for building Windows Desktop Applications. As such I decided my next personal project would involve WPF.

Given my wife and I plan our Disney trips on a desktop computer anyway as we find it easier to quickly access web pages with relevant information, creating my own tool for planning our trips seemed like a great fit!

## [Activity Planner Timetable Application (WPF)](https://github.com/ThomasFisherSE/ActivityPlanner)

_Note: This is an ongoing project at the time of writing this post, so keep in mind it is not complete yet._

The "Activity Planner" application (a better name may come later!) is a desktop application allowing users to specify activities and locations, assign activities to certain locations, and then assign activities to date/time slots. The application will then display a timetable showing when each activity will take place.

The application is built using the MVVM software architecture pattern.

As the project develops, I hope to post more information here, but in the meantime feel free to take a look at the GitHub project [here](https://github.com/ThomasFisherSE/ActivityPlanner).