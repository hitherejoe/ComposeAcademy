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

When it comes to single value animations, Jetpack Compose offers the following functionalities.

## Color animation

```kotlin
val enabled = state { true }
Clickable({ enabled.value = !enabled.value }) {
    Stack {
        Box(Modifier.fillMaxSize(), backgroundColor =
        animate(if (enabled.value) Color.Green else Color.Red))
        Text(text = "Click me to change color!")
    }
}
```

## Float animation

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
