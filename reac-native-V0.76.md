# React Native V0.76 🚀

Hey **React Native 💙** Developers,

The highlights are:

- **New Architecture now Default 🚀**
- **New React Native DevTools**
- **Expo SDK 52 beta released 🔥**
- **15x Faster Metro build 😱**
- **New boxShadow style props added**
- **New React Native Edge-to-Edge SDK 💯**
- **Android Apps now ~3.8Mb smaller and ~15ms less startup time 💯**

![0 76](https://github.com/user-attachments/assets/03817880-3249-4f5e-8a6c-641b8276601d)


Let’s dive into each of the new highlights.

# **New Architecture now Default 🚀**

​Since 2018, the React Native team worked on a New Architecture to replace the slow bridge (JSON communication) between JS and Native code (Swift, Kotlin). They created a C++ layer called JSI to speed up the communication. This new flow of communication is called New Architecture. In March 2022, it became an experimental option in React Native 0.68. Now, in 0.76, the New Architecture is production-ready 🔥

# **New React Native DevTools**

After 6 years of hard work and learning from all previous DevTools (JSC Debugger, Remote JS Debugger, Hermes Debugger, Flipper, Dev Menu), the team finally released the next-gen debugging stack & made it the default in 0.76. It can debug nearly every component of the Dev Environment (Hermes, Metro, React code). So, from 0.76 you don’t need any other Debugging Tools—just Chrome or Microsoft Edge installed on your device. No other setup is required 🤩

# **Expo SDK 52 beta released**
![unnamed](https://github.com/user-attachments/assets/091bb870-3eb5-49a9-aed4-9f852f78552e)

The Expo team released SDK 52 beta (stable within 2 weeks) with lots of exciting features, including React Native 0.76. The most exciting are:

1. **Expo DOM Component**
2. **Experimental Tree Shaking**

# **Expo DOM Component**

​DOM Components are super helpful for migrating a web app (like a React or Next.js app) to a mobile app (like a React Native app) or if you have a web library that isn't yet available for native Android or iOS. To save months of work, you can just create a DOM Component, and copy-paste your web code (like code with <div>, <h1>, etc.) into your Expo project, and write “use dom” at the top of the component (Expo JS file). Boom, your React (web) code now works smoothly in your native app 🔥

# **Experimental Tree Shaking**

SDK 52 adds experimental Tree Shaking support. This allows Expo to automatically remove unused imports and exports from your app. For example, if you use the lucide-react library and only need ChevronLeft and ChevronRighticons, Tree Shaking will keep just those icons in your app's JS bundle. Unused icons will be removed. One benchmark showed this can reduce bundle size by up to 87% 🚀.

![GY9XI4jbAAImTTx](https://github.com/user-attachments/assets/3507dc78-15c9-45be-971d-299cacfb63e1)

# **15x Faster Metro build 😱**


https://github.com/user-attachments/assets/e8199628-2793-4b4c-871a-e526d4f0c20d


Metro release included a bunch of performance improvements to our resolver, making it around 15x faster. That's especially good news for warm builds.

# **New boxShadow style props added**

![1729827440444](https://github.com/user-attachments/assets/765a2414-e93a-49d8-8b3a-2e143c2e5941)

boxShadow adds a shadow to an element, with the ability to control the position, color, size, and blurriness of the shadow.boxShadow can take either a string, which mimics the CSS syntax, or JS objects which can embed variables. For example the string ‘5 5 5 0 rgba(255, 0, 0, 0.5)’ and the object {offsetX: 5, offsetY: 5, blurRadius: 5, spreadDistance: 0, color: ‘rgba(255, 0, 0, 0.5)’}

# **New React Native Edge-to-Edge SDK 💯**
![unnamed](https://github.com/user-attachments/assets/d8879f10-5704-4a36-bd77-3ea13d551ef5)

Edge-to-edge means that the app content will use the entire screen, including areas under the device status bar(the bar that shows you time, battery charge, etc.) and the device navigation bar. Currently, edge-to-edge is optional for apps, but from Android 15, with the app's Target SDK level set to 35 or higher, edge-to-edge will be the only choice, and the status & navigation bars will be transparent. However, React Native 0.76 still uses Target SDK Level 34 as the default.

### Android Apps now ~3.8Mb smaller and ~15ms less startup time 💯

React Native 0.76 will ship with a reduced number of native libraries, as we merged a lot of our native code into a single library called libreactnative.so.

This change comes with reduction in app size, and improvement in app startup performance on Android.App size will be reduced by ~3.8MB (20% of the total) and median App startup time will be reduced by ~15ms (~8%)

# That's All 🙋‍♂️

I hope you enjoyed reading it. It would be really great if you could consider giving it a [**STAR**](https://github.com/avisek123/react-native-releases/blob/maste)
