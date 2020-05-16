---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Checked
description: Assert whether or not a composable is currently checked

# Micro navigation
micro_nav: false

---

## Assert a composable is checked

```kotlin
findByTag(tag).assertIsOn()
```

## Assert a composable is not checked

```kotlin
findByTag(tag).assertIsOff()
```