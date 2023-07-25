---
title: What is a PWA? 
description: What exactly is a Progressive Web App? Lets learn together!
date: 2023-07-25
---

Progressive Web Applications

You have probably heard of them, maybe have read a few articles on them, but, one thing I have personally found lacking is a clear answer to "What is a PWA?". Today, I hope to answer that question!

## What is a PWA?
At their simplest, a PWA is a web app that uses a [Web Manifest](https://docs.pwabuilder.com/#/home/pwa-intro?id=web-app-manifests), [https](https://www.cloudflare.com/learning/ssl/what-is-https/) and a [Service Worker](https://docs.pwabuilder.com/#/home/pwa-intro?id=service-workers). However, they are much much more than the technical requirements. Let's dive in!

### Best of Web + Native
Progressive Web Applications bring together the best of the web with the best of installed applications. Like a web app, they:

- Are cross-platform, including CPU architecture, by default
- Can be found and shared with just a URL
- Instant updates, no need to wait on the app stores
- Truly one codebase that runs everywhere

However, like a native app, they also:

- Can use low level APIs to integrate with the OS. For example, PWAs can use [shortcuts](https://docs.pwabuilder.com/#/home/native-features?id=shortcuts), [badging](https://docs.pwabuilder.com/#/home/native-features?id=badging) and even things like [custom titlebars](https://docs.pwabuilder.com/#/home/native-features?id=window-controls-overlay) and [Bluetooth](https://developer.mozilla.org/en-US/docs/Web/API/Web_Bluetooth_API)
- Can be published and installed from the app stores
- Show up as an app on the users OS, for example, on Windows they show up in the title bar, can be pinned to the desktop, show up in the settings app etc, just like a UWP app.
- Can work offline
- Work reliably on a bad network connection

This is a combination of features that, in the past, required a "hybrid" solution such as Electron, Cordova or Capacitor. However, with the power of the modern web platform, you can achieve the same with just web tech!

### Learn more on capabilities
The [Project Fugu Initiative](https://developer.chrome.com/blog/fugu-status/) is the best place to start learning about all the capabilities that PWAs have access too.

## Why build a PWA? 
Ther are many reasons you may want to build a PWA. Lets go over some of the common developer facing reasons, and then we will cover some benefits for your users!

### Developer facing
- Truly one codebase that runs everywhere. No need for a seperate android codebase, iOS codebase etc. No need for a hybrid codebase that has seperate code running in seperate environments. This is all pure web tech.
- Already a Web Developer? You have the skills to start building a PWA!
- No need for a thousand dollar laptop just so things compile quickly. PWAs can be built on anything from an affordable Windows device to a Chromebook.
- Develop the app in your browser, with extremely quick turnaround on code changes etc.
- App Distribution: You users can find your app anywhere, from the web to the app stores.

### User facing
- Much lighter weight than many native apps, and definitely lighter weight than Electron, Cordova or Capacitor apps. This means less storage space taken by your app, quicker start times and more for your users.
- Inclusiveness: PWAs dont require expensive, powerful devices to function well.
- Reliable on any network connection.
- Users can use your app in their preferred manner, from the browser to installing from an app store.

## Examples

The following are some of my favorite PWAs that I use all the time:
- [Squoosh](https://squoosh.app/)
- [Twitter](https://twitter.com/home)
- [Elk](https://www.microsoft.com/store/productId/9PNZMMXQHQZ5)
- [Memos AI (built by me)](https://www.recordergo.app)
- [Microsoft Designer](https://designer.microsoft.com/)
- [VSCode](https://vscode.dev/)


Get started building your PWA today with [PWABuilder](https://docs.pwabuilder.com/#/starter/quick-start)!!!!