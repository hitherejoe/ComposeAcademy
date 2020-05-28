---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Double Tap
description: A modifier used for detecting double tap gestures on views
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/core/gesture.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

Detecting a tap can be done by utilising the doubleTapGestureFilter  
when providing modifiers for your desired view:

```kotlin
Text(
    text = ("Double tap me!"),
    modifier = Modifier.doubleTapGestureFilter(onDoubleTap = {
        // handle double tap
    })
)
```
