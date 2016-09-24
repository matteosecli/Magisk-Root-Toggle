# Magisk Root Toggle
![Icon](magisk_root_toggle.png)


##Description

**Magisk Root Toggle** for Android aims to provide a quick 'n' dirty solution for enabling/disabling Magisk root permissions. It's basically a [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm) task packaged into a standalone app via [Tasker App Factory](https://play.google.com/store/apps/details?id=net.dinglisch.android.appfactory). The advantages of packaging the task are multiple:

- No need to install (i.e., buy) Tasker. **Magisk Root Toggle** is completely **free** (and **opensource**).
- \[CQS\] No foreground processes that drain your battery. In order to function properly, Tasker has ho run in foreground; when the task is packaged as an app, there is no need of this. Simply launch the app when you need it and you're good to go. To ensure that Tasker's monitor is not running after the closure of the app, **Magisk Root Toggle** includes a specific action that kills the process.
- \[CQS\] **Magisk Root Toggle** works in synergy with [Custom Quick Settings](https://play.google.com/store/apps/details?id=com.quinny898.app.customquicksettings) in order to provide an easy-to-use tile-experience. If you want to launch an app via Custom Quick Settings, then it's completely **free** (as in this case). If instead you want to launch a Tasker task, you have to buy the Pro version. Now tell me that I don't love you. ❤ 😄
- If you are really wondering why I did not make a simple app from scratch instead of all of this mess, then I honestly tell you: I am not an Android developer, I don't even know how to start designing an app (ok, that I actually know, maybe). Anyway, this app was just made for personal use and for a friend of mine who really wanna play Pokémon Go, so please understand my limits. 😜


## Target users

This app is made for **Android 6** users. If you are on **Android 7**, then I suggest to use [Magisk Quick Toggle](https://play.google.com/store/apps/details?id=me.bpear.magiskquicktoggle) which is much better than my own app.

There is also a great tool called [Automagisk](http://www.androidpolice.com/2016/09/18/automagisk-allows-root-users-play-pokemon-go-use-android-pay-without-constantly-toggling-root-off/) that should enable/disable root when you open an app that doesn't like root. It does work with Android Pay and Pokémon Go, but it doesn't with my banking app. So I still needed a quick way to enable/disable root at need; that's also why I made this app.


## Prerequisites

- Well, **Magisk** of course 😂. You can use the great [guide on Android Police](http://www.androidpolice.com/2016/09/11/guide-play-pokemon-go-0-37-rooted-android-magisk/) to install it.
- [Custom Quick Settings](https://play.google.com/store/apps/details?id=com.quinny898.app.customquicksettings) (or [QuickTask](https://play.google.com/store/apps/details?id=com.balda.quicktask)). Just install it via the Play Store; no need to buy the Pro version.
 

## Which version should I install?

**Magisk Root Toggle** comes in two flavors: a version which works for both Custom Quick Settings and QuickTask, and a version which only works with Custom Quick Settings. I'll try to explain pros and cons.

#### → Custom Quick Settings

**Pros:**

- Easier setup.
- No need to run **Magisk Root Toggle** as a background process, so it does not consume any resource.

**Cons:**

- You need to choose the icon on your own.
- More problematic (take a look at the issues labeled \[CQS\] in the section [Known issues](#known-issues)).

#### → QuickTask

**Pros:**

- The icon is set up automatically on **Magisk Root Toggle**'s first launch.
- It does not have all the problems that Custom Quick Settings has (tile connection and tile color).

**Cons:**

- Slightly more complicated setup.
- **Magisk Root Toggle** has to run as a background process, and *may* consume resources (even though, in my short-time tests, it did not consume anything relevant).


So, basically:

- If you want to use QuickTask or you are not sure, then download the version "**Magisk Root Toggle**".
- If you want to use Custom Quick Settings, download the version **Magisk Root Toggle (CQS)**.

## Installation

- Be sure to have "Unknown sources" enabled. To enable then, just go to "Settings -> Security -> Unknown sources" and toggle on.
- Download the most recent APK from my GitHub ([link to the latest version](https://github.com/matteosecli/magisk-root-toggle/releases/latest)).
- Install it (you may need to open it via a 3rd part file explorer such as X-plore, ES, FX, or whichever you like).
- \[CQS\] Now, open **Custom Quick Settings** (if instead you are using QuickTask, jump at the next point). If you have other custom tiles, **delete them**. This is important, as the tile we're going to create **has to be the first one created** (i.e., it has to have internal name "CUSTOMTILE0"). Then, create a new tile (allow forever superuser permissions to Custom Quick Settings if asked). Use the following settings (also check out [this great guide on Android Police](http://www.androidpolice.com/2015/10/30/hands-on-custom-quick-settings-adds-new-tiles-to-the-android-6-0-quick-settings-via-ui-tuner/) ):
    - The Title: "Root".
    - The Icon: Choose whichever icon you like from "Built in icons". I personally suggest "pound", it really feels like root! 
    - The Click Action: Choose "Launch App -> Magisk Root Toggle". Then press the confirmation icon to save and exit the app.
- \[QT\] If you want to use **QuickTask**, check that you've activated Android's "System UI Tuner" by long pressing the small settings icon (the "gear") in the drop down menu of your system. Then, go to "Settings -> System UI Tuner -> Quick Settings" and add a new "Broadcast Tile" named "magiskroottoggletile". Then, open QuickTask and create a new tile following the instructions ("QuickTask -> Tiles management -> + button"). Use the following settings:
    - Tile name: "magiskroottoggletile" (without quotes). **Important:** the "tile name" has to be **the same** as the one you've used when creating a new "Broadcast Tile" in "Settings -> System UI Tuner -> Quick Settings".
    - Tile label: "Root"
    - Do not care about the icon, it will be automatically changed by **Magisk Root Toggle**.
- A new tile should have appeared in your menu, named "Root". Tap on it and allow forever superuser permissions to **Magisk Root Toggle** if asked.
- If you are using the QuickTask version and the first tap on the tile does not do anything, open **Magisk Root Toggle** from the app drawer. It should be necessary only for the first time.

That's it! You've done it! 😄
If root is active the tile should be white-colored, whereas if root is not active the tile should be gray-colored.


## Known issues

- After using **Magisk Root Toggle**, you can of course use Magisk Manager to check root's status. Beware that if Magisk Manager was still running in backgound while you used **Magisk Root Toggle**, then it will report a **wrong** root status. To be sure, close Magisk Manager (via the "recent apps" screen) and open it again. After you use it, **close it** to avoid wrong reports. There is nothing I can do about this.
- \[CQS\] The tile is not changing color (white/gray). This means that there are issues in connecting the Tasker app (which changes its color after enabling/disabling root) to the tile itself. It could be that the tile was not assigned the "ID 0" because there were already other tiles. Repeat the procedure with Custom Quick Settings and make sure it's the **first** tile you create (so that it's assigned the ID 0). If the tile is not changing color, this **doesn't mean** that **Magisk Root Toggle** is not working! It's indeed working, but it's not changing the tile's color.
- \[CQS\] I deactivated root and the tile got gray (fine). But after a while, the tile got white again. What happened? Root is still deactivated, but it seems that after some time Custom Quick Settings checks again its own tiles and reset them to their default color (white). I still have to investigate further into this, but it seems to be a problem on Custom Quick Settings' side.
- All my tiles are gone! Don't worry; go to "Settings -> System UI Tuner -> Quick Settings -> Upper right menu (three vertical dots) -> Reset". Then, add back your "Root" tile.


## Support

No support here, I'm sorry. This is just a fun project and I don't really want to spend a lot of time on it. Still, if you have questions/suggestions/whatever, try to email me at <[secli.matteo@gmail.com](mailto:secli.matteo@gmail.com)> and I'll do what I can to help you.
If you find the app useful and you want to support me (I'm a student), you can make me happy by just [buying me a coffee](https://paypal.me/matteosecli)! 😊


## Source code

The code is under GPL-3.0. The sources are mainly two:

- **Magisk_Root_Toggle__CQS_.tsk.xml**, which is the Tasker task exported as a XML file. If you don't like the idea of an app and/or you want to tweak the task, it's there for you.
- **Magisk_Root_Toggle.prj.xml**, which is basically the same as "Magisk\_Root\_Toggle__CQS_.tsk.xml" but without the monitor killer and with a profile that listens for "tile tap" events. 
- **magisk_root_toggle.svg**, the app icon. I made it quickly with Inkscape (in fact, it's an "Inskscape SVG") but I'm not a designer. So don't be too tough on my design skills. Then, I exported the SVG into a PNG.

If you want to compile the task yourself into an app, just import the task in the XML format and choose your own icon (or the one in this repo), then long press -> Export as an app. You need [Tasker App Factory](https://play.google.com/store/apps/details?id=net.dinglisch.android.appfactory) to do that.
