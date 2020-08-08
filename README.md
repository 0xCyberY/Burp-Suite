# [Burp-Suite](https://tryhackme.com/room/rpburpsuite)

<h1>This is writeup for Burp Suite room in tryhackme.com</h1>

<h2>1. __Tasks__</h2>
  
  <h3>[Task 1] Intro</h3>
  
  Burp Suite, a framework of web application pentesting tools, is widely regarded as the de facto tool to use when performing web app testing. Throughout this room, we'll take a look at the basics of installing and using this tool as well as it's various major components. Reference links to the associated documentation per section have been provided at the bottom of most tasks throughout this room. 
  
![Image of burp](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/burpsuite.png)

The virtual machine used in this room (OWASP JuiceShop) can be installed from this [link](https://github.com/bkimminich/juice-shop#from-sources) or via [Heroku](https://elements.heroku.com/buttons/bkimminich/juice-shop) (in case that you'd like to do this room in a sort of offline mode, otherwise you can launch the VM below as per normal). The JuiceShop project is an intentionally vulnerable web application created as part of the OWASP project. 

Prior to attempting this room, I highly recommend checking out the ['Web Fundamentals'](https://tryhackme.com/room/webfundamentals) room by [NinjaJc01](https://tryhackme.com/p/NinjaJc01). If you are familiar with basic web request structure and SQL injection, you're already set!
  
 >#1	Read the overview and continue on into installation!>]<
 
    ✅ No answer needed
 ______________________________________________________________________________________________________________________________________________________
 
   <h3>[Task 2] Installation</h3>
  
Before we can dive into the pretty amazing tool that is Burp Suite, we'll first have to install it. Lucky for us, if you're doing this room on Kali Linux you'll already have Burp Suite installed. Since this room is entirely do-able on Windows as well, we'll briefly touch on obtaining Burp Suite (community edition) for any system as it's fairly painless. _You can also use deploy your own [in-browser machine](https://tryhackme.com/my-machine) with BurpSuite already installed!_

If you'll be installing Burp (as it's commonly referred to) from scratch, you'll need to first visit this [link](https://portswigger.net/burp/communitydownload)

![Image2](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/burp2.png) 

We'll use the Burp Suite Community Edition throughout this lab, however, I'll be covering some paid features briefly as well to help you prepare for eventually using the Professional version.

Burp Suite Getting Started Documentation: [Link](https://portswigger.net/burp/documentation/desktop/getting-started)

 >#1	If you'll be installing Burp (as it's commonly referred to) from scratch, you'll need to first visit this link: https://portswigger.net/burp/communitydownload

    ✅ No answer needed
    
 >#2	Once you've reached the Port Swigger downloads page, go ahead and download the appropriate version for your operating system
    
    ✅ No answer needed
    
 >#3	Burp Suite requires Java JRE in order to run. Download and install Java here: https://www.java.com/en/download/
Once you've got everything setup move onto our next task, Gettin' [CA] Certified!

    ✅ No answer needed

 ______________________________________________________________________________________________________________________________________________________
 
 <h3>[Task 3] Gettin' [CA] Certified</h3>
 
 Before we can start using our new installation (or preinstalled) Burp Suite, we'll have to fix a certificate warning. We need to install a CA certificate as BurpSuite acts as a proxy between your browser and sending it through the internet - It allows the BurpSuite Application to read and send on HTTPS data.
 
 ![connection](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/connectiom%20!.png)
 
 A certificate warning that will appear unless we install Burp's CA Certificate.

One quick note, in this lab I'll be using Firefox and Foxy Proxy (which you can find [here](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/)). I use Firefox in this instance as it's a little bit easier to work with when using Burp Suite. 

  >#1	First, let's go ahead and launch Burp. We can do this on Kali via the icon on the left side. In the image below it's the seventh icon from the top on the left-hand side. If your Kali desktop doesn't look like the screenshot below, click on 'Applications' and type in Burp Suite. Click on the Burp Suite icon that appears.
  
  ![burp_in_kali](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/burpkali.png)
  
  >Launch Burp!
  
    ✅ No answer needed
    
  >#2	Once you've launched Burp, you'll be greeted with the following screen:

![image_lunched](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/lunched%20burp.png)

Once this pops-up, click 'Temporary project' and then 'Next'.

*Now as you likely noticed both 'New project on disk' and 'Open existing project' are both grayed out. As annotated at the top of this window saving projects is a feature associated with Burp Suite Professional as it's pretty common to save and come back to a multi-day web application test. 

    ✅ No answer needed
    
  >#3	Next, we'll be prompted to ask for what configuration we'd like to use. For now, select 'Use Burp defaults'.
  
 ![image_defaults](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/defaults.png)
 
 This option is included as it can be incredibly useful to create a custom configuration file for your proxy or other settings, especially depending on how your network configuration and/or if Burp Suite is being launched remotely such as via [x11 forwarding](https://www.youtube.com/watch?v=auePeI8vZA8) 
 
    ✅ No answer needed
    
  >#4	Finally, let's go ahead and Start Burp! Click 'Start Burp' now!
  
    ✅ No answer needed
    
   >#5	You'll now see a screen that looks similar to this:
   
 ![Image_running burp](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/running%20burp.png)
 
 Since we now have Burp Suite running, the proxy service will have started by default with it. In order to fully leverage this proxy, we'll have to install the CA certificate included with Burp Suite (otherwise we won't be able to load anything with SSL). To do this, let's launch Firefox now!

*You can do this part with your browser of choice, however, I'll be using Firefox for this room.
   
   
    ✅ No answer needed

  >#6	Now that we've started Burp, let's add an extension to our web browser to allow up to easily route or traffic through it! For this room, we'll be using 'FoxyProxy Standard' on Firefox.
  
  ![Image_foxyProxy](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/foxypeoxy.png)
  
 Navigate to the following link to install FoxyProxy Standard: [Link](https://addons.mozilla.org/en-US/firefox/addon/foxyproxy-standard/)

Go ahead and install this now!

    ✅ No answer needed
    
  >#7	Next, click on FoxyProxy among your extensions.
  
  ![Image_extensions](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/extensions.png)
  
  After that, click on 'Options'.
  
  ![image_options](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/options.png)
  
  After that, click 'Add' in the top left.
  
  ![image_ADD](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/ADD.png)
  
  Enter in the following settings and then click 'Save'
  
  ![image_edit](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/Edit.png)
  
  Finally, click on the FoxyProxy extension icon again and select 'Burp'.
  
  ![image_selectBurp](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/selectBurp.png)
  
  In the image above Burp isn't selected. Make sure it is in yours!

Next, we'll move onto adding the certificate for Burp!


    ✅ No answer needed
    
  >#8	With Firefox, navigate to the following address: http://localhost:8080
  
    ✅ No answer needed
    
  >#9	You'll be greeted with the following website:

![imageBursuitecom...](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/BurpsuitCom...png)

Click on 'CA Certificate' in the top right to download and save the CA Certificate.

    ✅ No answer needed
    
  >#10	Now that we've downloaded the CA Certificate, move over to the settings menu in Firefox. Search for 'Certificates' in the search bar. 
  
  ![Image_search result](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/search%20result.png)
  
  Click on 'View Certificates'
  
    ✅ No answer needed
    
   >#11	Next, in the Authorities tab click on 'Import'

    ✅ No answer needed

   >#12	Navigate to where you saved the CA Certificate we downloaded previously. Click 'OK' once you've selected this certificate.
  
    ✅ No answer needed
    
   >#13	Finally, select the following two options seen in this photo:
   
![Image_download cer](https://github.com/abdullah-baghuth/Burp-Suite/blob/master/download%20Cert.png)

Select 'OK' once you've done this. Congrats, we've now installed the Burp Suite CA Certificate!

    ✅ No answer needed

_________________________________________________________________________________________________________________________________________________________________________

   <h3>[Task 4] Overview of Features</h3>
   
   Now that we've set up Burp, let's take a look at everything it has to offer. Web application pentesting can be a messy affair but Burp has something for every step of the way.
   Throughout this room, we'll be taking a look at these components of Burp Suite. Here's a quick overview of each section covered:

  * __Proxy__ - What allows us to funnel traffic through Burp Suite for further analysis
  * __Target__ - How we set the scope of our project. We can also use this to effectively create a site map of the application we are testing.
  * __Intruder__ - Incredibly powerful tool for everything from field fuzzing to credential stuffing and more
  * __Repeater__ - Allows us to 'repeat' requests that have previously been made with or without modification. Often used in a precursor step to fuzzing with the aforementioned Intruder
  * __Sequencer__ - Analyzes the 'randomness' present in parts of the web app which are intended to be unpredictable. This is commonly used for testing session cookies
  * __Decoder__ - As the name suggests, Decoder is a tool that allows us to perform various transforms on pieces of data. These transforms vary from decoding/encoding to various bases or URL encoding.
  * __Comparer__ - Comparer as you might have guessed is a tool we can use to compare different responses or other pieces of data such as site maps or proxy histories (awesome for access control issue testing). This is very similar to the Linux tool diff.
  * __Extender__ - Similar to adding mods to a game like Minecraft, Extender allows us to add components such as tool integrations, additional scan definitions, and more!
  * __Scanner__ - Automated web vulnerability scanner that can highlight areas of the application for further manual investigation or possible exploitation with another section of Burp. This feature, while not in the community edition of Burp Suite, is still a key facet of performing a web application test.

  >#1	Which tool in Burp Suite can we use to perform a 'diff' on responses and other pieces of data?

    ✅ Comparer
    
  >#2	What tool could we use to analyze randomness in different pieces of data such as password reset tokens?

    ✅ Sequencer

  >#3	Which tool can we use to set the scope of our project?

    ✅ Target
    
   >#4	While only available in the premium versions of Burp Suite, which tool can we use to automatically identify different vulnerabilities in the application we are examining?

    ✅ Scanner

   >#5	Encoding or decoding data can be particularly useful when examining URL parameters or protections on a form, which tool allows us to do just that?

    ✅ Decoder
    
   >#6	Which tool allows us to redirect our web traffic into Burp for further examination?

    ✅ Proxy
 
   >#7	Simple in concept but powerful in execution, which tool allows us to reissue requests?

    ✅ Repeater
    
   >#8	With four modes, which tool in Burp can we use for a variety of purposes such as field fuzzing?

    ✅ Intruder
    
   >#9	Last but certainly not least, which tool allows us to modify Burp Suite via the addition of extensions?

    ✅ Extender
    
________________________________________________________________________________________________________________________________________________________________________

    <h3>[Task 5] Engage Dark Mode</h3>





