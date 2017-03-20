---
id: 2
title: About
date: 2014-03-21T22:51:21+00:00
author: wehrdesigns@gmail.com
layout: default
guid: http://www.wehrdesigns.com/?page_id=2
---
The IoT system that I call the DISC System (Distributed Intelligent Sense and Control) was developed by myself, <a href="https://www.linkedin.com/in/nathan-wehr-aa3b6b31" target="_blank">Nathan Wehr</a>, for the purpose of honing my skills while producing a useful tool.  The system has been in development since 2008 and was released to the public in 2014.  I plan to keep the core components of the system (both hardware and software) as open source for the benefit of all.  The system is built on top of excellent open source tools that are very adaptable and extensible in their own right.  If you are excited about what you see, and want to provide encouragement, let me know at wehrdesigns@gmail.com.

**What is the DISC system being used for?**
  
I have moved a couple times since I designed the system and I found it very flexible and easy to set up in a new space.  It has accomplished quite a few tasks over the years such as recording temperature, humidity, light level and PIR motion from outside the home and for rooms inside the home.  It records power for electrical circuits (at the electrical panel).  It records weather data such as barometric pressure, wind speed and rain fall.  It allows remote control of the thermostat by interfacing to a commercial thermostat.  In addition to recording data, it can easily be configured to perform digital control of other circuits.  The system allows for automated decision making and control as well as manual control of digital outputs.

**Design Goals for the DISC System**

  * Networked &#8211; preferring a web interface over an application GUI
  * Keep the cost down &#8211; we don&#8217;t want to go in debt while we learn and we want to try lots of ideas!
  * Reliability &#8211; it should not crash while you are away and want to use the system remotely
  * Performance &#8211; I&#8217;m a test engineer and I want accurate data and precise control
  * Fault tolerant &#8211; components (harware or sofware) should operate in isolation when necessary and reconnect with no loss (or minimal loss) of information
  * Extensible &#8211; there will always be something we want to add so build the foundation to support change

**History of the DISC System**
  
The first system was written in perl and visual basic and the hardware circuits were overly complicated.  The front end web server has been apache.  After studying the available languages, python was chosen because it supports so many operating systems (linux, windows and mac), it is open, efficient and has extensive support from the science and technology community.  A design goal was to use a web interface rather than a stand alone application interface, so a web framework was needed.  Django was chosen because of the excellent admin interface, the ORM, support for sqlite, excellent documentation, continuous development and extensibility.  The microcontrollers were chosen from the MSP430 line when TI released their Launchpad development system that cost few dollars.  A wired sensor network was developed because it was more cost effective in some installations and has educational benefits.  Replacing wires with wireless (at the same cost) is a goal.  Sensor data is stored in a database and the initial database was Microsoft SQL Server.  This was replaced with sqlite to simplify installation and support more platforms.  One of the uses of sensor data is to make decisions.  This can be a heavy use of data so it should be locally available to the decision processes.  Initially the sensor data was stored as a value with a date stamp in the same was as about every other IoT time series database.  Data is easy to store and retrieve in this way but it is &#8220;unfiltered&#8221; and is more difficult (and slower) to use.  Cleaning up the data (at the time that it is retrieved) is slow and inefficient so a &#8220;filter&#8221; was created to clean up the data as it is being loaded into the database.  Physical data storage presented problems because constant writing to a hard drive can drastically shorten its life (I killed a couple drives BEFORE developing a memory cache).  Also, reading from a USB flash drive can be slow.  Sqlite provided a solution because it allows memory databases.  A software layer was created to cache recent data in memory and then write it to disk periodically.  As the software evolved new features, the hardware also improved.  The samewire network was developed to provide 12V power and half-duplex communication over two wires (one of them is ground) and a simple circuit of a diode, regulator, transistor, two capacitors and a few resistors.  The samewire network is reliable even when connected to a large network of wires such as &#8220;repurposed&#8221; telephone lines in the home (Note: the telephone lines must be disconnected from the telephone company, you can&#8217;t run the telephone and samewire network on the same lines at the same time).  Bluetooth class 2 and longer distance class 1 modules work reliably with the system.  I&#8217;m excited about writing code for the Wipy to work with this system, but I need time to work on it!

Any part of the DISC System may be upgraded at any time as I balance my time between hardware development and board design, firmware development, application development, ordering parts for development and alpha testing, building test systems, documentation of all of these pieces and maintaining this website.

If you have questions or encouragement, please email me at wehrdesigns@gmail.com.
