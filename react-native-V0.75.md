# React Native V0.75 🚀

Hey **React Native 💙** Developers,

The highlights are:

- **Yoga 3.1**

- **Solve textAlign not working with inline views on Android.**

- **Sunset of react-native-init command**

- **Recommendation to use Frameworks**

- **Expo SDK 51 supports**

- **Auto-linking performance improvements**

  ![1723693787094](https://github.com/user-attachments/assets/da210206-3174-4ebb-9bdf-89c84ab3cf77)

Let’s dive into each of the new highlights.

# **Yoga 3.1**

One of the most highly requested features is the support for **`%`** values in various places, such as **gap** properties (e.g., **`gap`**, **`rowGap`**, **`columnGap`**) and **translation** properties (e.g., **`translateY`**, **`translateX`** ). The great news is that **Yoga 3.1** now has this support 🚀.

Today we will explore the code for the **`gap`** property. Let’s take a look at the image below.

One of the most highly requested features is the support for **`%`** values in various places, such as **gap** properties (e.g., **`gap`**, **`rowGap`**, **`columnGap`**) and **translation** properties (e.g., **`translateY`**, **`translateX`** ). The great news is that **Yoga 3.1** now has this support 🚀.

Today we will explore the code for the **`gap`** property. Let’s take a look at the image below.

# **Solve textAlign not working with inline views on Android.**

As part of making the New Architecture stable, the team has fixed several bugs in **React Native 0.75**. One of them is “[**`textAlign`** not working with inline views on Android.](https://github.com/facebook/react-native/pull/44146)” The good news is that it has been fixed in **0.75** 🎯. Let’s take a look at the image below.

In the above image, we see **text** with an **image (react native logo)** as an inline view (meaning in the same line). To improve the UI, it is natural to want the **logo** to be centered along with the text when applying the **`textAlign`** property as the **`center`**. However, you may notice that on the left side of the above image, the React Native logo is not properly centered with the text, while on the right side, it is perfectly **centered** because of **React Native 0.75**. Amazing, right? Below is the code for the above image.

```jsx
// Component Code
function App() {
  return (
    <Text style={styles.text}>
      This is
      <Image source={{ uri: "REACT_NATIVE_LOGO_URL" }} style={styles.image} />
      an example of inline view with textAlign center.
    </Text>
  );
}

// Component Style
const styles = StyleSheet.create({
  text: {
    textAlign: "center", // This now works correctly with inline views
  },
  image: {
    width: 50,
    height: 50,
  },
});
```

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

I hope you enjoyed reading it. It would be really great if you could consider giving it a [**STAR**]
