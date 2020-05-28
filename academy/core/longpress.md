---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Long Press
description: A modifier used for detecting long press gestures on views
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/core/gesture.kt"
    external_url: true
    
# Micro navigation
micro_nav: false

---

Detecting a long press can be done by utilising the longPressGestureFilter  
when providing modifiers for your desired view:

```kotlin
 Text(
    text = ("Long press me!"),
    modifier = Modifier.longPressGestureFilter(onLongPress = { position ->
        // Handle long press interaction
    })
)
```
