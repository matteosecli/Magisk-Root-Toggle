# Magisk Root Toggle
![Icon](magisk_root_toggle.png)


##Description

**Magisk Root Toggle** for Android aims to provide a quick 'n' dirty solution for enabling/disabling Magisk root permissions. It's basically a [Tasker](https://play.google.com/store/apps/details?id=net.dinglisch.android.taskerm) task packaged into a standalone app via [Tasker App Factory](https://play.google.com/store/apps/details?id=net.dinglisch.android.appfactory). The advantages of packaging the task are multiple:

- No need to install (i.e., buy) Tasker. **Magisk Root Toggle** is completely **free** (and **opensource**).
- No foreground processes that drain your battery. In order to function properly, Tasker has ho run in foreground; when the task is packaged as an app, there is no need of this. Simply launch the app when you need it and you're good to go. To ensure that Tasker's monitor is not running after the closure of the app, **Magisk Root Toggle** includes a specific action that kills the process.
- **Magisk Root Toggle** works in synergy with [Custom Quick Settings](https://play.google.com/store/apps/details?id=com.quinny898.app.customquicksettings) in order to provide an easy-to-use tile-experience. If you want to launch an app via Custom Quick Settings, then it's completely **free** (as in this case). If instead you want to launch a Tasker task, you have to buy the Pro version. Now tell me that I don't love you. ❤ 😄
- If you are really wondering why I did not make a simple app from scratch instead of all of this mess, then I honestly tell you: I am not an Android developer, I don't even know how to start designing an app (ok, that I actually know, maybe). Anyway, this app was just made for personal use and for a friend of mine who really wanna play Pokémon Go, so please understand my limits. 😜


## Target users

This app is made for **Android 6** users (it should also work in **Android 5** and maybe even below, who knows).
If you are on **Android 7**, then I suggest to use [Magisk Quick Toggle](https://play.google.com/store/apps/details?id=me.bpear.magiskquicktoggle) which is much better than my own app.

There is also a great tool called [Automagisk](http://www.androidpolice.com/2016/09/18/automagisk-allows-root-users-play-pokemon-go-use-android-pay-without-constantly-toggling-root-off/) that should enable/disable root when you open an app that doesn't like root. It does work with Android Pay and Pokémon Go, but it doesn't with my banking app. So I still needed a quick way to enable/disable root at need; that's also why I made this app.


## Prerequisites

- Well, **Magisk** of course 😂. You can use the great [guide on Android Police](http://www.androidpolice.com/2016/09/11/guide-play-pokemon-go-0-37-rooted-android-magisk/) to install it.
- [Custom Quick Settings](https://play.google.com/store/apps/details?id=com.quinny898.app.customquicksettings). Just install it via the Play Store; no need to buy the Pro version.


## Installation

- Be sure to have "Unknown sources" enabled. To enable then, just go to "Settings -> Security -> Unknown sources" and toggle on.
- Download the most current APK from my GitHub ([link to the latest version](https://github.com/matteosecli/magisk-root-toggle/releases/latest)).
- Install it (you may need to open it via a 3rd part file explorer such as X-plore, ES, FX, or whichever you like).
- Now, open Custom Quick Settings. If you have other custom tiles, **delete them**. This is important, as the tile we're going to create **has to be the first one created**. Then, create a new tile (allow forever superuser permissions to Custom Quick Settings if asked). Use the following settings:
    - The Title: "Root".
    - The Icon: Choose whichever icon you like from "Built in icons"
    - The Click Action: Choose "Launch App -> Magisk Root Toggle". Then press the confirmation icon to save and exit the app.
- A new tile should have appeared in your menu, named "Root". Tap on it and allow forever superuser permissions to **Magisk Root Toggle** if asked.

That's it! You've done it! 😄
If root is active the tile should be white-colored, whereas if root is not active the tile should be gray-colored.


## Known issues

- After using **Magisk Root Toggle**, you can of course use Magisk Manager to check root's status. Beware that if Magisk Manager was still running in backgound while you used **Magisk Root Toggle**, then it will report a **wrong** root status. To be sure, close Magisk Manager (via the "recent apps" screen) and open it again. After you use it, **close it** to avoid wrong reports. There is nothing I can do about this.
- The tile is not changing color (white/gray). This means that there are issues in connecting the tasker app (which changes its color after enabling/disabling root) to the tile itself. It could be that the tile was not assigned the "ID 0" because there were already other tiles. Repeat the procedure with Custom Quick Settings and make sure it's the **first** tile you create (so that it's assigned the ID 0). If the tile is not changing color, this **doesn't mean** that **Magisk Root Toggle** is not working! It's indeed working, but it's not changing the tile's color.


## Support

No support here, I'm sorry. This is just a fun project and I don't really want to spend a lot of time on it. Still, if you have questions/suggestions/whatever, try to email me at <[secli.matteo@gmail.com](mailto:secli.matteo@gmail.com)> and I'll do what I can to help you.
If you find the app useful and you want to support me (I'm a student), you can make me happy by just [buying me a coffee](https://paypal.me/matteosecli)! 😊


## Source code.

The code is under GPL-3.0. The sources are mainly two:

- **Magisk_Root_Toggle.tsk.xml**, which is the Tasker task exported as a XML file. If you don't like the idea of an app and/or you want to tweak the task, it's there for you.
- **magisk_root_toggle.svg**, the app icon. I made it quickly with Inkscape (in fact, it's an "Inskscape SVG") but I'm not a designer. So don't be too tough on my design skills. Then, I exported the SVG into a PNG.

If you want to compile the task yourself into an app, just import the task in the XML format and choose your own icon (or the one in this repo), then long press -> Export as an app. You need [Tasker App Factory](https://play.google.com/store/apps/details?id=net.dinglisch.android.appfactory) to do that.
