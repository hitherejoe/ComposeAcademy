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

## Constructors

```kotlin
@Composable
fun <T> Crossfade(
    current: T,
    animation: AnimationBuilder<Float> = TweenBuilder(),
    children: @Composable() (T) -> Unit
)
```

* **current** – the current state of the animation. When this is changed, the crossfade will be performed to this value
  * required

* **animation** – the animation used for the crossfade. By default this will be the tween animation

* **children** – the child composables that are being animated
  * required

## Examples

```kotlin
val strings = listOf("This the first text", "This is the second text")
var currentString by state { strings[0] }

Column(modifier = Modifier.fillMaxWidth()) {
    Crossfade(current = currentString) { color ->
        Text(color, modifier = Modifier.fillMaxWidth().clickable(onClick = {
            currentString = if (currentString == strings[0]) strings[1] else strings[0]
        }),
        style = TextStyle(textAlign = TextAlign.Center))
    }
}
```
