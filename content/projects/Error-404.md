---
title: "Error 404"
date: 2023-04-01T17:14:44+01:00
draft: true
author: Rhoda
tags:
image: /images/404Banner.avif
description:
---

Hey there!

Let's take a look at what happens when you enter a URL into your browser’s address bar.

When you tell your browser you want to visit www.aliexpress.com, your browser is clueless. It doesn't know where that is, which is why it has to translate that address *(www.aliexpress.com)* to a format it can read. This process is called DNS resolution(Don’t worry if you don't know what that is).

Your browser contacts a DNS server and a conversation like this happens.

*Browser: Hey, My boss wants to visit www.aliexpress.com. Any idea where that is?*

*DNS server: Sure. You’ve come to ask the right person. That is located at 47.254.175.252*

Your browser then sends a request to *47.254.175.252* (You can paste this in your browser and see what happens). This is known as the IP address which help devices and servers find and communicate with each other and every device (phones, laptops, MiFis, etc) and server has an IP address

After your browser sends a request to the web server(a.k.a www.aliexpress.com, a.k.a  47.254.175.252),  the server receives and processes the request, and then sends back the relevant resources(HTML, CSS, JavaScript, and other resources that make up the web page)

<!-- An  Image -->  
<div align="center">
    <img src=/images/4041.webp>
</div>

 <br>  


After the web server sends the response, your browser has to render the response properly so you see this:

<!-- An  Image -->  

<div align="center">
    <img src=/images/4042.webp width="65%" height="35%">
</div>

 <br>  

Instead of this:

<!-- An  Image -->  

<div align="center">
    <img src=/images/4043.webp width="40%" height="60%">
</div>

 <br>  

One of the resources the server sends back to the browser is an “HTTP header” which contains the HTTP(Hypertext Transfer Protocol) status code for that request.

The status code gives more information about the status of your request and you most likely won't see the status code unless there is a problem.

There are quite several status codes but they are divided into the 5 classes listed below:

Informational (1xx): These status codes are used to provide information about the request, such as that the request was received and is being processed.

Successful (2xx): These status codes indicate that the request was successful and everything is working well

Redirection (3xx): These status codes indicate that the requested resource has been moved to a new location, and the client should try again at the new location.

Client Error (4xx): This indicates that something has gone wrong. Most likely from your end(The client). You have made an error such as requesting a resource that doesn't exist or you didn't provide the necessary authentication credentials. 

Server Error (5xx): These status codes indicate that there is an error from the server (probably the server has more requests than it can handle or the server is down for whatever reason) and you usually can’t fix this unless you are the owner of the website.

I will just touch on a  couple of the more common ones you might have come across but you can read this documentation here to learn more about others.

The classes of code that usually indicate a problem are the 4XX and 5XX classes.

<!-- An  Image -->  

<div align="center">
    <img src=/images/4044.webp width="65%" height="35%">
</div>

 <br>  


400: This usually occurs due to an incorrectly typed URL, malformed syntax, or a URL that contains illegal characters. So you have to be careful when typing your URL.

<!-- An  Image -->  

<div align="center">
    <img src=/images/4045.webp>
</div>

 <br>  



403: You usually get this error when you attempt to access something that you don’t have permission to view. For example, trying to reach password-protected content without logging in might produce a 403 error.

<!-- An Image -->

<div align="center">
    <img src=/images/4046.webp width="65%" height="35%">
</div>

 <br>  


404: You might have come across any variation of this error such as  “Error 404”, “Page Not Found”, “The page cannot be found”, “We can’t find the page you’re looking for” or some other funny variations. What this error means is that the server cannot find the page you are requesting for. This error will usually show up if the page you are looking for has been removed or you typed the wrong address such as rhododendron.com/sendMeMoney but rhododendron.com does not have a sendMeMoney page.

<!-- 2  Images -->  

<div align="center">
    <img src=/images/4047.webp>
</div>

 <br>  

<div align="center">
    <img src=/images/4048.webp>
</div>

 <br>  


Finally, you have the error 418 which you get when you tell your teapot to brew coffee for you😂😂😂😂

<!-- An  Image -->  

<div align="center">
    <img src=/images/4049.webp width="65%" height="35%">
</div>

 <br>  

The most common error in the 5XX class is the 503 error(Service Unavailable) which you get when the server is unable to handle your request due to the server being under maintenance or there is too much traffic than it can handle.

<!-- An  Image -->  

<div align="center">
    <img src=/images/40410.webp>
</div>

 <br>  

So, the next time you get an error, I hope you can figure out what went wrong and how you can fix it.