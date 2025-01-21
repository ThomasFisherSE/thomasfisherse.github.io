---
layout: post
published: true
title: Activity Planner Desktop App
subtitle: A Windows desktop application built using WPF providing activity planning capabilities.
gh-repo: ThomasFisherSE/ActivityPlanner
gh-badge: [star, follow]
tags: [C#,XAML,.NET,WPF,Desktop,Windows,Development,Projects]
thumbnail-img: "/assets/img/projects/activityplanner/AssignActivityTimeSlot.png"
cover-img: ["/assets/img/projects/activityplanner/AssignActivityTimeSlot.png"]
---
{: .box-note}
**Note:** This project is a work in progress, and is something I'm working on occassionally in my spare time. I will continue to update this article as the project progresses.

## Introduction
My main personal project at the moment is to create a planner app for planning activities over a particular time span (e.g. for a holiday itinerary).

### Motivation
#### Planning Disney

One of the biggest shared interests between myself and my wife is our love of Disney. Specifically, the theme parks like those at Walt Disney World in Florida. We both enjoyed the theme parks with our families when we were younger, but have carried it into our adult life too, choosing Disney World as our main holiday destination most times we take a trip.

As anyone familiar with going to Disney parks in the last few years can attest to, it can get a bit complicated. There are all sorts of aspects of the holiday to consider:
- Restaurant reservations
- Park reservations
- "Fastpass" reservations for reduced waiting times
- Timed or even dated events / activities / shows
- Dining & drinks packages
- Plenty more

We are meticulous planners. Rather than going with the flow and seeing where the day takes us, we prefer a carefully thought out itinerary, planned with both enjoyment and efficiency in mind.

##### Spreadsheets Aren't Cutting It

Whenever we plan a Disney parks trip, we usually set up a huge spreadsheet with Google Sheets detailing what we plan to be doing each day. It would have colour coded locations, such as which park a particular activity would take place in. We'd add icons as notation for various attributes like "this restaurant needs a reservation", or "this restaurant is available on the Disney dining plan". We also use the spreadsheet for some analysis and plan refinement, like counting how many hours we are spending at each park to determine whether we're spending enough time at each park.

Using spreadsheet software, this can be quite a time consuming task, and it doesn't look that great in the end since our planning approach isn't really what spreadsheet applications are designed for.

![Holiday planning spreadsheet example](/assets/img/projects/activityplanner/spreadsheet.png)

#### Expanding my Skills

I'm always keen to hone my skills in different tools and technologies. Something I've had experience with for internal projects at work, but that I wanted to freely explore further, is WPF. As such I have been considering doing a personal project using WPF. 

Given we always plan our Disney trips on a desktop computer as we find it easier to quickly access web pages with relevant information, creating my own desktop app with WPF for planning our trips seemed like a great fit.

## [Activity Planner Timetable Application (WPF)](https://github.com/ThomasFisherSE/ActivityPlanner)

_Note: This is an ongoing project at the time of writing this post, so keep in mind it is not complete yet._

The "Activity Planner" application (a better name may come later!) is a desktop application allowing users to specify activities and locations, assign activities to certain locations, and then assign activities to date/time slots. The application will then display a timetable showing when each activity will take place.

The application is built using the MVVM software architecture pattern.

As the project develops, I hope to post more information here, but in the meantime feel free to take a look at the GitHub project [here](https://github.com/ThomasFisherSE/ActivityPlanner).

## Current Capabilities
Currently the application has the following capabilities:
- Define location data
  - Specify location name
- Define activity data
  - Specify activity name
  - Specify location
  - Optionally specify an icon
- Assign time range(s) for activities
- Visualize activity time slots in timetable
  - Programatically generated timetable grid based on data range and time span per row
- Saves and loads session data (JSON Serialization / Deserialization)

## Screenshots
![Activity Planner: Assigning an Activity Time Slot](/assets/img/projects/activityplanner/AssignActivityTimeSlot.png)

More to come as the project progresses.

## Future Improvements
### Canvas-Based Timetable View
Currently, the timetable view in the application is using a basic `Grid` control, where each grid cell is programatically populated based on user-entered timing data. For prototyping this has been a convenient intiial solution, however it has its drawbacks. 

For example, if an activity starts mid-way through a time slot, there is currently no way to visualize this to differentiate the fact that it didn't start at the beginning of the time slot.

To address this and provide much better flexibility, I intend to use a canvas for the timetable view instead, drawing activity 'blocks' with complete flexibility without being bound to grid rows / columns. This way, if an activity starts / ends mid-way through a time slot, the code that draws the block can simply choose the pixel to start the visualization at based on how far into the time slot the activity takes place.

### Iconography in Timetable View
One of the elements we tend to include in our plans is iconography to denote certain things about an acitivity block. For example, if a restaurant may require a reservation, we'd put a pen icon next to its name. 

I plan to introduce this capability to the app by showing an acitvity's icon (if specified by the user) in the timetable slot for that activity.

### Color-Coding Locations
To easily identify locations that activities take place in (for example, which theme park it takes place in when on our Disney trips), we tend to color code locations. In the Disney World example, Magic Kingdom might be blue, Animal Kingdom might be green etc.

An improvement I plan to make soon is to allow a color to be specified when a user defines a location, and to then visualize this color in the timetable by changing the background color of that activity slot.

### Data Input UI Improvements
At the moment, data input is carried out through simple dialogs that I have implement as a quick initial solution for prototyping. I intend to replace each of these dialogs with more thought-out, polished user interfaces.