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

Starting from December 31st 2024, the init command won’t create a project anymore. You will have to either:

- Use a framework such as Expo, with its own dedicate command to create a new project, such as
  **`npx create-expo-app`**.

- Invoke the Community CLI directly with **`npx @react-native-community/cli init`**.
  ![0 75-deprecation-6b1313b48e5c70e39c32db72f9a1fad8](https://github.com/user-attachments/assets/b0f2205f-0844-4a37-a479-6a28ec14c6cd)

