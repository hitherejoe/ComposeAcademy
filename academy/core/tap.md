---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Tap
description: A modifier used for detecting tap gestures on views

# Micro navigation
micro_nav: false

---

Detecting a tap can be done by utilising the tapGestureFilter when providing modifiers for your desired view:

```kotlin
Text(
    text = ("Tap me!"),
    modifier = Modifier.tapGestureFilter(onTap = {
        // handle tap
    })
)
```
