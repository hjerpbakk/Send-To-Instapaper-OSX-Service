OS X Service: Send to Instapaper
==============================

***tl;dr***

*Send to Instapaper* is an OS X 10.8 (or later) service used to send URLs to Instapaper from any link in any app:

> 1. Add a *Instapaper* record to *Keychain* with your Instapaper username and optional password.
> 2. **[Download](LINK)** and install the service.
> 3. Right click on any link in any app and choose *Services -> Send to Instapaper*.

***Background***

[Instapaper](http://clkuk.tradedoubler.com/click?p=24369&a=2174073&url=https%3A%2F%2Fitunes.apple.com%2Fno%2Fapp%2Finstapaper%2Fid288545208%3Fmt%3D8%26uo%3D4%26partnerId%3D2003) is still my *read it later* service of choice. It is widely supported, but I wanted the possibility to send URLs to Instapaper from *any* app in OS X. 

The *Send to Instapaper* OS X service works in any app that hasn't completely customized its context menu (I'm looking at you Kindle). Even Apple's own apps now support Instapaper 👍

***Installation***

In order to use this service, you need an [Instapaper account](http://www.instapaper.com/). 

Add an *Instapaper* record to *Keychain* using the *Keychain Access* app. Input your Instapaper username and password. If you do not use a password, anything can be written in the password field.

<img style="display:block; margin-left:auto; margin-right:auto;" src="http://hjerpbakk.com/storage/post-images/InstapaperKeychainRecord.png" alt="Instapaper Keychain record with account name and optional password" title="Instapaper Keychain record with account name and optional password" border="0" width="388" height="365" />

**[Download](LINK)** and extract the service. Open the service to install it (double click or *right click -> Open*).

***Usage***

Right click on any link in any app and choose *Services -> Send to Instapaper*. The screenshot below shows a link being sent from [ReadKit](http://clkuk.tradedoubler.com/click?p=24369&a=2174073&url=https%3A%2F%2Fitunes.apple.com%2Fno%2Fapp%2Freadkit%2Fid588726889%3Fmt%3D12%26uo%3D4%26partnerId%3D2003):

<img style="display:block; margin-left:auto; margin-right:auto;" src="http://hjerpbakk.com/storage/post-images/SendToInstapaper.png" alt="Send to Instapaper" title="Send to Instapaper" border="0" width="453.5" height="265" />

The URL from the link will be extracted and sent to Instapaper. After it is successfully added to your Instapaper queue, a notification will appear showing the sent URL:

<img style="display:block; margin-left:auto; margin-right:auto;" src="http://hjerpbakk.com/storage/post-images/InstapaperNotification.png" alt="Instapaper notification" title="Instapaper notification" border="0" width="324,5" height="98" />

If the selected text contained multiple links, the last one will be sent.

***Source***

I've uploaded the source to [this repository at GitHub](https://github.com/Sankra/Send-To-Instapaper-OSX-Service). The automator service is a mix between shell and python scripts, together with some standard Automator actions. The structure is as follows:

1. Extract a URL from the selected text.
2. Find the user's username and password in Keychain.
3. Send the URL to Instapaper.
4. Show a notification to user.

I use [terminal-notifier](https://github.com/alloy/terminal-notifier) to show OS X notifications.
