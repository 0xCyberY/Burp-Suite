# [Burp-Suite](https://tryhackme.com/room/rpburpsuite)

<h1>This is writeup for Burp Suite room in tryhackme.com</h1>

<h2>1. __Tasks__</h2>
  
  * [Task 1] Intro
  
  Burp Suite, a framework of web application pentesting tools, is widely regarded as the de facto tool to use when performing web app testing. Throughout this room, we'll take a look at the basics of installing and using this tool as well as it's various major components. Reference links to the associated documentation per section have been provided at the bottom of most tasks throughout this room. 
  
![Image of burp](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/burpsuite.png)

The virtual machine used in this room (OWASP JuiceShop) can be installed from this [link](https://github.com/bkimminich/juice-shop#from-sources) or via [Heroku](https://elements.heroku.com/buttons/bkimminich/juice-shop) (in case that you'd like to do this room in a sort of offline mode, otherwise you can launch the VM below as per normal). The JuiceShop project is an intentionally vulnerable web application created as part of the OWASP project. 

Prior to attempting this room, I highly recommend checking out the ['Web Fundamentals'](https://tryhackme.com/room/webfundamentals) room by [NinjaJc01](https://tryhackme.com/p/NinjaJc01). If you are familiar with basic web request structure and SQL injection, you're already set!
  
  <h3>#1	Read the overview and continue on into installation!</h3>
  
 - [x] `No answer needed`
 
 ______________________________________________________________________________________________________________________________________________________
 
  * [Task 2] Installation
  
Before we can dive into the pretty amazing tool that is Burp Suite, we'll first have to install it. Lucky for us, if you're doing this room on Kali Linux you'll already have Burp Suite installed. Since this room is entirely do-able on Windows as well, we'll briefly touch on obtaining Burp Suite (community edition) for any system as it's fairly painless. _You can also use deploy your own [in-browser machine](https://tryhackme.com/my-machine) with BurpSuite already installed!_

If you'll be installing Burp (as it's commonly referred to) from scratch, you'll need to first visit this [link](https://portswigger.net/burp/communitydownload)

......................................![Image2](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/burp2.png)

We'll use the Burp Suite Community Edition throughout this lab, however, I'll be covering some paid features briefly as well to help you prepare for eventually using the Professional version.

Burp Suite Getting Started Documentation: [Link](https://portswigger.net/burp/documentation/desktop/getting-started)
