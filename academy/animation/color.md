---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Single Value Animation
description: Used to create simple animations between single values
buttons:
 	  - icon: github
      content: View in Playground
      url: 'https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/animation/singleValueColorAnimation.kt'
      external_url: true

# Micro navigation
micro_nav: false

---

## Construction

When creating a single value color animation there are three properties which can be provided:

* **target** – the target value to be animated to
  * required
* **animBuilder** – the animation builder depicts ho the animation beteen the values will be performed
* **endListener** – listen for when the animation has completed

```kotlin
@Composable
fun animate(
    target: Color,
    animBuilder: AnimationBuilder<Color> = remember { PhysicsBuilder() },
    endListener: ((Color) -> Unit)? = null
)
```

## Example animation

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
