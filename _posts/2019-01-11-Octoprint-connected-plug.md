---
title: Octoprint connected plug
date: 2019-01-11 01:30:00 -500
categories: [DIY,hardware,3dprinter]
tags: [octoprint,diy,projetcs] #tag is always lower case
---

## Intro

I've started some home automation recently, and I've also been testing octoprint ( I have it installed back in the day but was not super happy with the performance ( disconnection / lag ) - I decided to swap my SD card and use a proper 3A USB power plug and since then I'm please with my Octoprint setup), As I said on top - I've started to get some home automation done in the appartment using Alexa and some smart plug. In this How to, I'll be explaining how to integrate a smart plug from TPlink (not super expensive) in order to have your printer to shutdown once finish, you'll see that super easy.

## Step 1

Get the Smart Plug from TPLink, it's would be possible to have it done like DIY but for 35euros, we will save time, have a more reliable setting and the hassle of the setup. On top of that you can always shutdown the printer even if you're not at home from the TP Link application.

![TPLink ender3](https://i.gyazo.com/efc1fb19eaca1dab0f33a5c75c56ac31.jpg)

To setup the plug that super easy, you'll have to download the TP Link application [iOS link](https://itunes.apple.com/us/app/kasa-smart/id1034035493?mt=8){:target="_blank"}/[Android link](https://play.google.com/store/apps/details?id=com.tplink.kasa_android&hl=fr){:target="_blank"} - Once installed on your phone, plug your Smart Plug into the power socket, launch the APP and follow the instruction to connect the Plug to your home network, it won't take long.

Once done we will have to find the IP details of your plug, you can do that by going under your router page and check for the DHCP  IP that was given by your router itself - or you can use an app on your phone called [Fing iOS](https://itunes.apple.com/us/app/fing-network-scanner/id430921107?mt=8){:target="_blank"} / [Fing Android](https://play.google.com/store/apps/details?id=com.overlook.android.fing&hl=fr){:target="_blank"} this app will scan your network and discover for you all the devices plugged into your network - the plug will be listed (I still recommand checking the router page as you can validate the IP by checking the mac address details of the plug ( this is a physical address that attributed to the device itself by the manufacturer))

Once this is done you can move to Step2. But before that - you can connect the power cord of your printer in your smartplug and turn the power supply of your printer to ON position.

## Step 2

You would need to install Octoprint TP Link plugin, for that head over the wrench on the top right corner

![Wrench](https://i.gyazo.com/7aa49ec05e2d58b477bbd86748bbc957.png)

Once there, go to your Plugin Manager

![Plugin manager octoprint](https://i.gyazo.com/1dce9709b8d031c4f9bd5fe82c666129.png)

Click on Get More and search for TP Link SmartPlug, you can install it and you will have to reload when prompt by octoprint

Once Octoprint is reloaded, go back to your parameter and under plugins on the left you should see something called TP-Link smartplug

![Smart Plug](https://i.gyazo.com/4ef5efa75a54f3620759eb7387e9a1bd.png)

Click on that and click on the little pencil to edit the plug - You will have to enter the IP of your SmartPlug & a Label - you will also have to click on GCODE Trigger as per the screenshot below (please note that your IP should be different then mine)

![TPLink smart plug settings](https://i.gyazo.com/690402618c8a42b8223366fcec2b4192.png)

At this stage, your setup is almost finish, you can now try to turn on the printer by pressing the little Bolt on top

![Bolt status](https://i.gyazo.com/81031de902b1c9ecd7d8a4e888cd9b88.png)

It should light Green or Red depending of the state of the printer, you should have the printer turning ON or OFF - you would need to trigger the power button to ON in your printer in order to have it working properly, remember the plug will allow the voltage to flow to the printer moving forward!

FINAL STEP 3!

## Step 3 ( Cura )

Remember we had check the GCODE Trigger activate in the Step 2 - This will allow to trigger ON or OFF the printer by having a new ending script GCODE line, M81 follow by the IP of the smartplug will allow you to shutdown the printer once the print is finish

if you're using Cura, please head under your Printer ending script settings located under: **Settings > Printer > Manage Printer > Choose your printer and hit Machine settings**

![Cura machine settings](https://i.gyazo.com/445c142e38fb7952d43eef2d33eab49a.png)

Once you are on your machine settings, you can then add a M81 <IP> ( remove the <> ) under the End G-code section same as the screen below but remember to match with your current IP and **voila** 🤩

![Cura End Gcode](https://i.gyazo.com/cfc8370f55ada19148b9a01f03639df5.png)

## Step 3 (Simplify 3D)

If you're using Simplify 3D - same step apply, but in different location, Edit your Process by double clicking on it

![Simplify 3d edit process](https://i.gyazo.com/a92ce2b87d47f1f190a039ef2f335350.png)

Go Under: **Scripts > Ending Scripts** In order to add the M81 <IP> Line

![Simplify 3d ending scripts](https://i.gyazo.com/faaa1fe408cf205acd17ec29df9c763c.png)

Do not forget to save/Update your profile and and **Voila** 🤩

## Conclusion

This is a good addition to Octoprint in effort to make your setup more efficient and silent, why would the printer run all night if you're print finish at 2AM and you're sleeping?

happy printing! 😀
