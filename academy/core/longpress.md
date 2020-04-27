---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Long Press
description: A modifier used for detecting long press gestures on views

# Micro navigation
micro_nav: false

---

# Detecting long press

Detecting a long press can be done by utilising the longPressGestureFilter when providing modifiers for your desired view:

```kotlin
 Text(
    text = ("Long press me!"),
    modifier = Modifier.longPressGestureFilter(onLongPress = { position ->
        // Handle long press interaction
    })
)
```
