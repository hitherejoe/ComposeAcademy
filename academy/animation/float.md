---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Single Value Animation
description: Used to create simple animations between single values

# Micro navigation
micro_nav: false

---

When creating a single value float animation there are three properties which can be provided:

* **target** – the current state of the animation. When this is changed, the crossfade will be performed to this value
  * required
* **animBuilder** – the animation used for the crossfade. By default this will be the tween animation
* **endListener** – the child composables that are being animated

## Float animation

```kotlin
@Composable
fun animate(
    target: Float,
    animBuilder: AnimationBuilder<Float> = remember { PhysicsBuilder() },
    endListener: ((Float) -> Unit)? = null
)
```

```kotlin
val enabled = state { true }
Clickable({ enabled.value = !enabled.value }) {
    Stack(modifier = Modifier.padding(
      animate(if (enabled.value) 0f else 100f).dp)
    ) {
        Box(Modifier.fillMaxSize(), backgroundColor = Color.Green)
        Text(text = "Click me to change padding!")
    }
}
```
