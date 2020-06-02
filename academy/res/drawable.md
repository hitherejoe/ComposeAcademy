---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Drawables
description: Used to access drawables from an applications resources
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/resource/drawableResource.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Accessing a vector resource

Using the **vectorResource** function, a single vector drawable resource can be accessed.

```kotlin
vectorResource(id = R.drawable.ic_baseline_account_circle_24)
```

## Accessing an image resource

Using the **imageResource** function, a single image drawable resource can be accessed.

```kotlin
imageResource(id = R.drawable.outline_accessibility_black_18dp)
```