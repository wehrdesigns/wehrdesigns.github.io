---
id: 18
title: Learn about the DISC System
date: 2014-03-21T21:55:21+00:00
author: wehrdesigns@gmail.com
layout: default
guid: http://www.wehrdesigns.com/?page_id=18
image: /wp-content/uploads/2014/03/DISC_System_2014_3_15-455x270.jpg
---
### What is the DISC System?

  * An IoT system that is optimized to run on low powered computers such as the Raspberry Pi or Beaglebone.
  * It is written in Python and is fully web based using Django as the web framework.
  * It provides for collecting time series data, displaying the data and creating actions from that data.
  * At the core of the system is a server that filters and records numeric time series data and automatically creates averages of that data for quick viewing or using with actions.  Most systems record data &#8216;ad hoc&#8217; and leave the filtering to the end user.  The DISC Server handle data filtering from the front end.
  * The server includes django &#8220;apps&#8221; that make it easy to configure various sources of data.  Importantly, the server relates, but disconnects the sources of data from the consumers of data.
  * The system includes hardware and software.  The hardware might be sensors located around a home or business.  A software &#8220;controller&#8221; reads the sensors and sends data to the DISC Server.
  * The system includes a decision making &#8220;app&#8221; that operates on data in order to send notifications or direct hardware to perform actions.
  * The system makes it easy to write new &#8220;apps&#8221; that plug into the server.   The new app might be a derivative of an existing app or provide entirely new functionality.
  * The DISC Server is written in Python with the goal of remaining cross-platform (Linux, Windows, Mac (need a tester)).

#### So how can I use the DISC System?

First, you will use the system to collect sensor data.  Next, you can use the system to view and analyze the sensor data.  After you understand the data you can set up actions to start controlling your environment.  An action might be sending a text message or email or controlling a relay or executing a python script to perform several tasks.

#### Examples of questions that the system might answer:

  * Are there lights on in a room with no one there? 
      * Install a motion detector and light level sensor or current monitor in the room to be monitored
      * Configure how often the system should check the room, and how it should notify you.  Example: Text to speech will talk to you, or SMS or email will alert you.
  * Want a sleep quality report? 
      * Install a motion detector in your bedroom.
      * Configure the system to send you a report in the morning with total activity for the night as well as your longest period of stillness and when it occurred.  Later, check a graph to see how peacefully you slept.
  * Is there water running when it shouldn&#8217;t be?  Do you want to limit water usage or maybe your well has limited capacity? 
      * Install a power monitor on the electrical wire going to your well pump.
      * Configure the system to alert you when the well pump has been used running too long.
  * Want to know the status of an appliance such as how fast dryer is getting the clothes dry? 
      * Install a temperature and humidity sensor in the dryer exhaust.
      * Configure the system to tell you (tts) how the humidity is decreasing.  The temperature sensor helps the system automatically report when the dryer is running.
  * The National Weather Service provides a lot of forecast data, but how well does it match with the temperature on my front porch? 
      * Install a networked temperature sensor on your porch and log data to the disc server
      * Log the 12 hour forecast data from the NWS to the disc server
      * After a few days, plot the difference and learn what the offset is and how it varies in different weather conditions.
      * If you need to know about freezing temperatures, get a text message in the evening notifying you of the low temperature forecast.
  * How much does it cost for my hot shower? 
      * Install a networked power monitor on your electrical circuits and log data to the disc server
      * Get a text message after your shower that tells you the cost of the shower.
  * Will it be cool enough to open the windows tonight? 
      * You are already recording the temperature and humidity forecast and you know how it compares with your house, right?
      * You started a script that checks the forecast data and compares it with your comfort range and sends you a notice to open the windows (or directly operate your motorized windows).
  * Is there electricity being used when there should not be? 
      * Get a text message to alert you about changes in your environment

This is an open source system that is available for free.  There is no support number to call, but you can inspect the inner workings and modify and improve it for your needs.  You can contribute to improving the system and also benefit from others who improve the system.

If you have questions, email me at wehrdesigns@gmail.com.

&nbsp;

#### Learn about the DISC Server with a live demo.

Use the login &#8220;guest&#8221; and password &#8220;guest&#8221;.  The demo is configured very simply and there is no data.  Mostly, you will see tools used to configure the system.  There is one data channel loaded called &#8220;test 1&#8221;.  Plots of the data will be zero or a sloped line.  You can look around to get an idea of what is available in the system.  <a href="http://nwehr.pythonanywhere.com/disc/env/urls" target="_blank">There is some help built into the system</a>.  If you must add or change things in the demo, try not to mess it up too badly.  Your actions are tracked by django&#8217;s built in action tracker.

<a title="DISC Server Login" href="http://nwehr.pythonanywhere.com/disc/admin/login/" target="_blank">Click to go to the live demo</a>

<a title="DISC Server Docs" href="http://disc-server-docs.readthedocs.org/en/latest/" target="_blank">Check out the full documentation</a>

Note: because there is no live data in the demo, there may be a few things don&#8217;t work or even cause a crash.

Send an email with questions or comments to: wehrdesigns@gmail.com
