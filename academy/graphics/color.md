---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Color
description: Create color references for styling composable properties
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/graphics/color.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

When it comes to color references, there are a collection of ways to obtain and create colors for styling purposes

## Predefined Color values

```kotlin
Color.Red,
Color.Green,
Color.LightGray,
Color.DarkGray,
Color.Black,
Color.White,
Color.Cyan,
Color.Blue,
Color.Gray,
Color.Magenta,
Color.Transparent,
Color.Yellow,
Color.Unset
```

## Color from Long value
    
```kotlin
Color(0xFF000080)
```

## Color from Float values

```kotlin
Color(
    red = 1.0f,
    green = 0f,
    blue = 0f,
    alpha = 1f
)
```

## Coor from RGBA values

```kotlin
Color(
    red = 255,
    green = 0,
    blue = 0,
    alpha = 1
)
```
