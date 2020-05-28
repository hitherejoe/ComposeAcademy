---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Single Float Value Animation
description: Used to create simple animations between single float values
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/animation/singleValueFloatAnimation.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

When creating a single value float animation there are three properties which can be provided:

* **target** – the target value to be animated to
  * required
* **animBuilder** – the animation builder depicts ho the animation beteen the values will be performed
* **endListener** – listen for when the animation has completed

```kotlin
@Composable
fun animate(
    target: Float,
    animBuilder: AnimationBuilder<Float> = remember { PhysicsBuilder() },
    endListener: ((Float) -> Unit)? = null
)
```

## Example animation

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
