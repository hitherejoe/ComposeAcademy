---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Crossface
description: Used to animate between different states

# Micro navigation
micro_nav: false

---

When it comes to the crossfade animation, Jetpack Compose offers the following functionalities.

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
