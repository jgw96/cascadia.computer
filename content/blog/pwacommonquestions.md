---
title: Progressive Web Apps - An Intro + Answering some common questions 
description: In this post I will give a quick intro to PWAs and will then answer some common questions about PWAs!
date: 2024-01-17
---

Hello! Today I want to dive a little deeper and answer some common questions about Progressive Web Applications (PWAs) that I get, but dont see answers often to "in the wild". Let's start with a small intro, and then we will dive into the questions! We will then wrap up with an overview of some advantages PWAs have over platform-specific(native) apps.

## What is a PWA?

Progressive Web Applications (PWAs), at their most basic, are web apps that use modern web capabilities; at least a Web App Manifest and Service Worker, to enable advanced, native app like experiences on a user's device. PWAs can be installed through the browser, which will give the user a special install prompt if the browser detects a Web App Manifest and Service Worker, and installed through app stores, such as the Microsoft Store, Google Play and the Meta app store. 

Beyond just a Web App Manifest and Service worker though, PWAs also have access to many advanced, low-level capabilities that web apps historically have not had access to. This includes things such as:

- [Shortcuts (also known as Jumplists on certain OS’s)](https://docs.pwabuilder.com/#/home/native-features?id=shortcuts)
- [Bluetooth](https://medium.com/going-fullstack/interact-with-bluetooth-devices-using-the-web-bluetooth-api-7984b2509939)
- [NFC](https://developer.chrome.com/docs/capabilities/nfc)
- [USB](https://developer.chrome.com/docs/capabilities/usb)
- [3D and 2D graphics](https://developer.mozilla.org/en-US/docs/Web/API/WebGL_API)
- [GPU access for rendering and compute](https://developer.chrome.com/blog/webgpu-cross-platform/)
- [Camera access and control](https://developer.chrome.com/blog/imagecapture/)
- [Push Notifications](https://docs.pwabuilder.com/#/home/native-features?id=push-notifications)
- [Custom Titlebars](https://docs.pwabuilder.com/#/home/native-features?id=window-controls-overlay)
- [Share](https://docs.pwabuilder.com/#/home/native-features?id=web-share-api)
- [Receiving shared content](https://docs.pwabuilder.com/#/home/native-features?id=how-to-share-to-your-pwa)
- [Writing and reading from the file system](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps-chromium/how-to/offline#file-system-access)
- [Animations, including page transitions](https://developer.chrome.com/docs/web-platform/view-transitions/)
- [Can work totally offline](https://learn.microsoft.com/en-us/microsoft-edge/progressive-web-apps-chromium/how-to/service-workers)
- [Sync data in the background](https://docs.pwabuilder.com/#/home/native-features?id=background-sync)
- [Web Components, a component model built right into the browser](https://developer.mozilla.org/en-US/docs/Web/API/Web_Components)

And much more!

Many of these APIs have historically required you to use Electron, Cordova or some other WebView solution, you can now achieve the same functionality using JavaScript running in your browser.

## Common Questions

While the above description gives a good overview of PWAs, let's dive into some common questions I get about them, and hopefully my answers provide clarity.

- Aren’t the APIs mentioned above Web APIs, not PWA APIs?  

Yes! Many of the APIs can be used in a normal web app running in a browser tab. However, others, like shortcuts for example, require an installed PWA. A simple way to look at it is “All web APIs are PWA APIs, but not all PWA APIs are web APIs.”. However, all the capabilities are still just JavaScript running in the browser engine, the only difference is whether your app is running as an installed app (the user has installed it from the browser or app stores) or in a browser tab.

- Can PWAs also run in a browser tab?  

Yes! PWAs are basically advanced web apps, so they work perfectly fine in a normal browser tab, just like any other web app or web site. However, they can also run as installed apps! This means that users can get into your experience in whichever way they choose, whether through an app stores or browser, with no install needed to get started through the browser!

- Are PWAs still using the same browser engine, JavaScript engine etc as my default browser?  

Yes! You can think of installed PWAs as running in a “headless” browser tab. It looks like a webview app, but it's running in the browser.

- Are PWAs supported in all browsers?  

Yes, but with some caveats that you may be used to from feature checking for APIs such as Promises in the past. So, all PWAs are just HTML, CSS and JavaScript, atleast initially served from a web server, just like anything on the web. Because of this, they will work, atleast at some basic level, on any browser! However, this does not mean that, if your app relies on one of the advanced APIs I mentioned above, it will work in any browser. While many of the above APIs are supported cross-browser, some are Chromium only, and some are Chromium and Firefox only. Safari has historically had very limited support for anything beyond the basics in a PWA, this has been changing fast over the last 2-3 years because of social pressure, political pressure and market pressures.  

- Like in a WebView based app, can I write code that runs outside of the browser that I can call from my JavaScript?  

No, you cannot. This would break a few of the key advantages PWAs have, including the fact that this would prevent the app from running in the browser, plus would mean that your app is calling code that is running outside of the browsers sandbox, potentially opening security holes.

- What operating systems support PWAs?

Any OS that can run a modern browser, especially chromium-based browsers. Windows, Android, macOS, ChromeOS and Linux all have great support for PWAs. IOS and iPadOS have been held back for years on PWAs, but this is rapidly improving over the last two years.

Hopefully this answers some of the questions you had about Progressive Web Apps!

## Advantages of PWAs over native apps

PWAs are not the right stack for every app type out there, and there are of course places where platform-specific (native) apps will have their place, but PWAs can work for most apps AND provide key advantages over native apps:

- True write once / deploy everywhere experience, even to app stores! Because a PWA is just a web app, it will run anywhere with no code changes, no webview, no plugins that you must code around to get working in the browser, no platform specific code etc.

- Can be installed from both the browser and app stores, widening the reach of your application and enabling you to acquire users from multiple channels at once, with just one codebase.  

- Users can jump right into your app through the browser, no need to install anything. This leads to much lower friction-to-entry for users.

- Tend to be lighter weight on both storage size and resource usage than a native app, even with the same functionality.  

- Its all just standard web development skills, so if you are a web developer, you can be an app developer with PWAs, no new learning needed.

- They run in the browsers sandbox, with much finer grained user control over specific actions. For example, to access the clipboard, a user will see a permission prompt first, making it clear what is happening to the user. This is a much stronger level of control than users have over native apps. PWAs cannot start up random processes, cannot start reading and writing random files, and have heavy protection against fingerprinting etc.

Get started building your new PWA today at [Progressive Web App Intro Workshop](https://docs.pwabuilder.com/#/home/pwa-workshop).  
