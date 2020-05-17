---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Spacer
description: A layout composable sized via its modifiers, creating a visual space between any surrounding components

# Micro navigation
micro_nav: false

---

## Constructor

```kotlin
@Composable
fun Spacer(modifier: Modifier)
```

## Creating a spacer

When creating a spacer we make use of its modifiers to declare the space that it should occupy. For example, we can create a spacer with a specified height using the preferredHeight modifier.

```kotlin
Spacer(modifier = Modifier.preferredHeight(16.dp))
```

This allows us to create specific spaces between different composables. For example, instead of using the Columns arrangement property we might want to provide individual spaces between the child composables:


```kotlin
Column(
    modifier = Modifier.fillMaxSize().padding(32.dp)
) {
    Text(
        text = "First item"
    )
    Spacer(modifier = Modifier.preferredHeight(16.dp))
    Text(
        text = "Second item"
    )
    Spacer(modifier = Modifier.preferredHeight(32.dp))
    Text(
        text = "Third item"
    )
}
```

![Column](/academy/layout/media/spacer.png)

