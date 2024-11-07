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

![1723693787094](https://github.com/user-attachments/assets/da210206-3174-4ebb-9bdf-89c84ab3cf77)

Let’s dive into each of the new highlights.

# **New Architecture now Default 🚀**

​Since 2018, the React Native team worked on a New Architecture to replace the slow bridge (JSON communication) between JS and Native code (Swift, Kotlin). They created a C++ layer called JSI to speed up the communication. This new flow of communication is called New Architecture. In March 2022, it became an experimental option in React Native 0.68. Now, in 0.76, the New Architecture is production-ready 🔥

# **New React Native DevTools**

After 6 years of hard work and learning from all previous DevTools (JSC Debugger, Remote JS Debugger, Hermes Debugger, Flipper, Dev Menu), the team finally released the next-gen debugging stack & made it the default in 0.76. It can debug nearly every component of the Dev Environment (Hermes, Metro, React code). So, from 0.76 you don’t need any other Debugging Tools—just Chrome or Microsoft Edge installed on your device. No other setup is required 🤩

# **Expo SDK 52 beta released**

The Expo team released SDK 52 beta (stable within 2 weeks) with lots of exciting features, including React Native 0.76. The most exciting are:

1. **Expo DOM Component**
2. **Experimental Tree Shaking**

# **Expo DOM Component**

​DOM Components are super helpful for migrating a web app (like a React or Next.js app) to a mobile app (like a React Native app) or if you have a web library that isn't yet available for native Android or iOS. To save months of work, you can just create a DOM Component, and copy-paste your web code (like code with <div>, <h1>, etc.) into your Expo project, and write “use dom” at the top of the component (Expo JS file). Boom, your React (web) code now works smoothly in your native app 🔥

# **Sunset of react-native-init command**

Historically, **`react-native init`** was the default command to create new React Native projects. However, in 2024, we feel this command does not provide the same onboarding experience that a framework would offer you. That is why we are not recommending it anymore, instead you should use a framework like Expo.

You can still use **`react-native init`** to create new projects using the Community CLI & template today, but you will see the following warning:

![0 75-deprecation-6b1313b48e5c70e39c32db72f9a1fad8](https://github.com/user-attachments/assets/b0f2205f-0844-4a37-a479-6a28ec14c6cd)

Starting from December 31st 2024, the init command won’t create a project anymore. You will have to either:

- Use a framework such as Expo, with its own dedicate command to create a new project, such as
  **`npx create-expo-app`**.

- Invoke the Community CLI directly with **`npx @react-native-community/cli init`**.

# **Recommendation to use Frameworks**

Here's a chart that presents what the **Core** of React Native can do and what a **Framework** (such as Expo) can do. Let’s take a look at the chart below.

From the above image, the brown sections show the responsibilities of the Core of React Native, and the green sections show the responsibilities of a Framework. At the present moment, we are very lucky that the Expo team has created a production-grade framework for us, which provides all the necessary tools (mentioned in the chart above) to make our app ready for the Apple and Play Stores without any hassle. Finally, we can recall a quote from the stage of React Conf, which highlights the need for a framework.

# **Expo SDK 51 supports**

We can now say that **Expo** is an integral part of React Native, as it is the [**only react native framework**](https://reactnative.dev/blog/2024/06/25/use-a-framework-to-build-react-native-apps) with huge popularity due to its complete package of production-grade app development tools. The **Expo** team also sees this and has quickly added support for **React Native 0.75** with **Expo SDK 51**

# **Auto-linking performance improvements**

To understand better, let’s first understand a bit of Auto-linking.

### What is Auto-linking?

Auto-linking is a feature introduced in **React Native 0.60** that simplifies the process of **linking** native modules (connecting native code with JS code) to your React Native project. Before **`Auto-linking`**, when you added a new library, you would need to manually link it to your project using tools like **CocoaPods** for **iOS** or **Gradle** for **Android**. **Auto-linking** automates this process, making it easier to install any native modules (libraries) with a simple install command without additional configuration.

### Two Steps of Auto-linking

When a developer runs an **npm** or **yarn** command to install a **native module** package into a React Native app, the package is first downloaded into the app’s **`node_modules`** directory. After the installation is complete, the **auto-linking** process starts. This auto-linking process is completed in **two** steps.

1. **`Discovery Process Step:`** This process again has two steps.
   1. **`Scanning:`** Right after the native module is downloaded, the **core** of React Native scans your entire project to find the newly added library.
   2. **`Identifying:`** After scanning, the **core** of React Native identifies the newly installed library and gathers information about it, such as its configuration and dependencies.
2. **`Code Generation Step:`** Once the **discovery process** is complete, the **core** of React Native now generates the necessary code to link the library’s **native code** to your project’s **JS code**.

### Performance Boost in 0.75

As **Expo** is the only recommended framework by the **React Native team**, both teams made a great decision to split the responsibility of **auto-linking** into two parts, which created a significant performance boost. From now on, the **`Discovery Process Step`** (shown above) will be handled by the **Expo** framework, and the **`Code Generation Step`** will be managed by the **core** of React Native 🔥.

With **Expo SDK 51** and **React Native 0.75**, the auto-linking step for React Native libraries (which are not [**Expo modules**](https://docs.expo.dev/modules/overview/)) is now faster — up to **~6.5x faster** on **Android** and **~1.5x faster** on **iOS**. 🚀.

# That's All 🙋‍♂️

I hope you enjoyed reading it. It would be really great if you could consider giving it a [**STAR**](https://github.com/avisek123/react-native-releases/blob/maste)
