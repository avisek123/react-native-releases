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
