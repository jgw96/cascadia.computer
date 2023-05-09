---
title: How do I, a web developer, build an app?
description: 
date: 2023-05-09
---

It's a story as old as time itself, you are a web developer and you want to build an app. You want that app to be on the web of course, but ALSO be in the app stores. What do you do? You can go the hybrid route, like with React Native, or you can build a Progressive Web App(PWA). But, if you go the PWA route, can you put it in the app stores still? And, if you go the hybrid route, what do you lose on the web side of things? Let's dive in.

## What is a PWA? What is a hybrid app?

### PWA
A Progressive Web Application (PWA) is a type of web app that combines the best features of native apps and websites. A PWA can run on any device and browser, and can work offline or on low-quality networks. A PWA can also access device capabilities such as camera, microphone, push notifications, and more through web standard APIs. A PWA is fast, reliable, and engaging for users, and can improve the performance and user experience of web apps.

However, PWAs may have less access to operating system-specific APIs than hybrid applications. This issue has been addressed in a large way by the Project Fugu initiative. Nonetheless, hybrid and native apps will always have access to the latest native capabilities quicker than PWAs.

### Hybrid App
A hybrid app uses a common web technology stack, such as HTML, CSS, and JavaScript, to create a user interface that can run on multiple platforms. Additionally, a hybrid app can use a native wrapper such as React Native or Flutter along with plugins to access the device’s features. However, this also leads to the largest advantage for React Native: platform-specific native capabilities can be accessed relatively easily. In contrast, in the web world, capabilities must be built into the browser as web APIs which can take much longer to actually be implemented in browsers.

This native wrapper means that hybrid apps must be distributed as “bundles” that include both the web code and native code for each platform. This makes them larger than PWAs and more difficult to maintain.

## PWAs in the app stores
One of the biggest disadvantages traditionally of PWAs was the fact that you could not ship them to app stores without wrapping them in a hybrid wrapper. There are multiple problems with this, however the two most impactful are that you then no longer have one codebase that can easily run on the web, and that your code may need to be updated to work in a webview compared to the actual browser.

However, this is no longer the case. There are projects, such as [PWABuilder](https://www.pwabuilder.com) (disclaimer, I work on PWABuilder at Microsoft) that allow you to easily package your PWA for the Microsoft Store and Google Play, with experimental support for the Apple App Store. Importantly, this works by using the native support built into these stores for PWAs to enable you to ship your PWA with no wrapper needed. You simply package your PWA as an MSIX or APK (for Windows and Android respectively) and publish them to the store, just like you would with a native app. And, I think this is really cool, all you need is the URL to your PWA to do this. There are no wrappers, no extra build tools, no native SDKs to install.

## Hybrid apps on the web
Let's look at this from the [React Native](https://github.com/facebook/react-native) point of view.

React Native is a framework that allows you to build native mobile apps using JavaScript and React. However, you may also want to ship your React Native app to the web, so that users can access it from any browser. How do you do that?

One option is to use react-native-web, a library that implements React Native components and APIs for the web. This way, you can reuse most of your React Native code and create a web version of your app with minimal changes. To use react-native-web, you need to install it as a dependency and configure your bundler (such as webpack) to alias react-native to react-native-web. You also need to make sure that your app uses only the components and APIs that are supported by react-native-web, or provide fallbacks for the ones that are not.

Another option is to use Expo, a platform that simplifies the development and deployment of React Native apps. Expo provides a web browser target that allows you to run your React Native app in the browser using react-native-web under the hood. To use Expo, you need to install the Expo CLI and initialize your project with expo init. Then, you can run expo start --web to launch your app in the browser. You can also use Expo to build and publish your web app with expo build:web and expo publish:web.

As you can see, while it is possible, it does take extra tools, and work, to ship your hybrid app to the web. In fact, if your components are not supported by react-native-web, it can be ALOT of work. 

## Next Steps

At the end of the day, whether you should build a PWA or hybrid app can come down to many factors. My goal with this blog is not to say which one you should choose, as it is app and situation specific. My goal was instead to show that shipping to the app stores is not a blocker for going with a PWA, and that it is possible to take your React Native app to the web.

Be on the lookout for a post about when you should build a PWA, and when you should build a hybrid app. Thanks!