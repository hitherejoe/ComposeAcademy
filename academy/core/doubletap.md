---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Double Tap
description: A modifier used for detecting double tap gestures on views

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
