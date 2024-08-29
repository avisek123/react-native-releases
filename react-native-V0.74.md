# React Native V0.74 🚀



Hey **React Native 💙** Developers,

The highlights are:

- **Yoga 3.0**

- **New Architecture: Bridgeless by Default**

- **New Architecture: Batched onLayout Updates**

- **Yarn 3 for New Projects**

Let’s dive into each of the new highlights.

# Yoga 3.0

Let's understand first what **yoga** is in React Native.

### Yoga — the layout engine

Yoga is an open-source **layout engine** developed by Meta. The engine which refers to **how UI elements** (such as buttons, text, images, etc.) are **arranged** and **positioned** within a user interface.

Yoga calculates these four for each UI element.

1.  **Positioning**

2.  **Sizing**

3.  **Alignment**

4.  **Spacing**

With **Yoga**, you can create **responsive layouts** that adapt to different screen sizes and orientations. It also implements a widely used concept called **CSS Flexbox** in React Native. So you already feel that yoga is the heart (♥︎) of React Native flexible UI.

### Yoga 3.0 — what’s new?

In all previous versions of React Native, there were some incorrect layout behaviors. **Yoga 3** solved all of them. One of the most common issues was that the **‘row-reverse’** style was not functioning properly.

Let’s look at the image below where the **left** one is from **V0.73** and the **right** one is from **V0.74**.


![Bridgeless mode (1)](https://github.com/user-attachments/assets/00ce2106-083c-4515-880c-5fff7d9eedc2)

In the above image, we have a **\<Container/>**, then inside it a **\<Parent/>** component, then inside **two \<Box/>** components.

We then applied this style in the **\<Parent/>** component.

```javascript
    // Style for <Parent/> component
    style={{
          flexDirection: 'row-reverse',
          backgroundColor: 'lightblue',
          flex: 1,
          marginLeft: 100,
          marginRight: 20,
          marginVertical: 20,
          alignItems: 'center'
    }}
```

Did you notice, that we added a **marginLeft** of **100** pixels for **\<Parent/>**?

- Yeah, but see the output in React Native **V0.73** (the left one) from the above image. It shows a 100 pixels margin on the **right (not on the left)**!!

- Okay, now let’s see the output of React Native **V0.74** (the right one). Great, in V0.74 we see a perfect 100-pixel margin at **left,** and also two **\<Box/>** components got **reversed** 🚀

So, in Yoga-2, if you apply a **‘row-reverse’** flex-direction with **“margin”** or **“padding”** or **“border”** in a component then the edges of that component also get flipped. But in Yoga-3 it has been solved perfectly 💯

**Yoga-3** has brought some other important styling components that were missing in Yoga-2.

- **'space-evenly'** property for alignContent style

- **'static'** property for position style

# **New Architecture: Bridgeless by Default**
From **V0.74**, once you enable the New Architecture, you will see that **‘Bridgeless Mode’** has been enabled **automatically**. However, the New Architecture itself is still not yet enabled by default.

When you enable New Architecture in your React Native app with **V0.74**, you will see these **two lines** like the below in your Metro Log:

![Bridgeless mode (2)](https://github.com/user-attachments/assets/1842f93a-ec11-4949-861c-f60baa0643a7)

# **New Architecture: Batched onLayout Updates**

Another great news is that the React Native team not only made the New Architecture **Bridgeless Mode** the default, but they also improved this architecture to handle batched **onLayout** updates (executing multiple updates in a single rendering). This optimization enhances performance by minimizing layout-related computations during rendering.

### The “onLayout” props

The onLayout prop in React Native is used to handle **layout (position)** changes for a component. When the layout of a component changes (due to mounting, resizing, rotation, or other factors), the onLayout callback function is triggered.

You can use this prop like below to **perform actions** based on the updated layout information.

```javascript
function App() {
  return (
    <View
      onLayout={() => {
        console.log("Component has been invoked 🚀");
      }}
    />
  );
}
```

### How “onLayout" batch update works?

Assume the component **\<App/>** is as shown below, where each **View** triggers an **onLayout** callback function when mounted.

```javascript
function App() {
  const [state1, setState1] = useState(false);
  const [state2, setState2] = useState(false);
  const [state3, setState3] = useState(false);

  console.log("✅ COMPONENT RE-RENDERED .....");

  return (
    <View>
      <View
        onLayout={() => {
          console.log("FIRST View invoked");
          setState1(true); // Update state1 when the View mounts
        }}
      ></View>

      <View
        onLayout={() => {
          console.log("SECOND View invoked");
          setState2(true); // Update state2 when the View mounts
        }}
      ></View>

      <View
        onLayout={() => {
          console.log("THIRD View invoked");
          setState3(true); // Update state3 when the View mounts
        }}
      ></View>
    </View>
  );
}
```

Now, in React Native **V0.73**, you will see an output like below 👇

Did you notice that, on each execution of the **“onLayout”** callback, it re-renders the whole component? Yeah, it is not expected.

Now, let’s see the output in React Native **V0.74** with enabling **New Architecture** 👇


![Bridgeless mode](https://github.com/user-attachments/assets/f85f192c-5b51-410c-b40d-38d69abeb681)

Amazing performance 🔥. The component got re-rendered only once for all 3 **“onLayout”** callback execution.

# **Yarn 3 for New Projects**
<img width="651" alt="Screenshot 2024-08-29 at 12 17 13 AM" src="https://github.com/user-attachments/assets/b5381449-ca06-40ce-b283-ab5ac045f219">

**Yarn 3** is now the default JavaScript package manager for new projects initialized with React Native Community CLI. This replaces Yarn Classic **(1.x)**, which was deprecated and previously used as the default.

Yarn 3 speeds up the process of installing and updating dependencies and optimizes how dependencies are stored.


# **Android app size reduction**

![0 74-android-app-size-4200c5fc0a6daaff0b2a377c6f77af2c](https://github.com/user-attachments/assets/160ce907-fa98-4db8-a9f7-da397693e01f)


