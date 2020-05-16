---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Compose Test Rule
description: Used to animate between different states

# Micro navigation
micro_nav: false

---

## Set content

In cases where we just need to render a composable and perform tests on it, we can use the setContent function on our compose rule reference. When we call this we need to provide the composable which is to be rendered on screen.

```kotlin
@get:Rule
val composeTestRule = createComposeRule()

composeTestRule.setContent {
    MaterialTheme {
        Surface {
            // your composable content for testing
        }
    }
}
```
