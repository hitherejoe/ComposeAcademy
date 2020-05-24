---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Crossfade
description: Used to animate between different states

# Micro navigation
micro_nav: false

---

When creating a crossfade animation there are three properties which can be provided:

* **current** – the current state of the animation. When this is changed, the crossfade will be performed to this value
  * required
* **animation** – the animation used for the crossfade. By default this will be the tween animation
* **children** – the child composables that are being animated
  * required

```kotlin
@Composable
fun <T> Crossfade(
    current: T,
    animation: AnimationBuilder<Float> = TweenBuilder(),
    children: @Composable() (T) -> Unit
)
```

## Animate between states

```kotlin
val strings = listOf("This the first text", "This is the second text")
var currentString by state { strings[0] }

Column(modifier = Modifier.fillMaxWidth()) {
    Clickable(onClick = {
        currentString = if (currentString == strings[0])
            strings[1] else strings[0]
    }) {
        Crossfade(current = currentString) { color ->
            Text(color, modifier = Modifier.fillMaxWidth(),
                style = TextStyle(textAlign = TextAlign.Center))
        }
    }
}
```
