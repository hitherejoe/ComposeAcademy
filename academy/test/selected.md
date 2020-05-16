---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Selected
description: Assert whether or not a composable is currently selected

# Micro navigation
micro_nav: false

---

## Assert a composable is selected

```kotlin
findByTag(tag).assertIsSelected()
```

## Assert a composable is not selected

```kotlin
findByTag(tag).assertIsUnselected()
```