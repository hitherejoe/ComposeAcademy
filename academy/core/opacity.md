---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Opacity
description: A modifier used for applying opacity to a composable
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/core/opacity.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
drawOpacity(0.2f)
```

## Example

```kotlin
Box(
    modifier = Modifier.preferredSize(100.dp, 100.dp).drawOpacity(0.2f),
    backgroundColor = Color.Green
)
```

![Opacity](/academy/core/media/opacity.png)
