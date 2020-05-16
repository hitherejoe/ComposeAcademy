---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Hidden
description: Assert whether or not a composable is hidden from view

# Micro navigation
micro_nav: false

---

## Assert a composable is hidden

```kotlin
findByText(hint).assertIsHidden()
```

## Assert a composable is not hidden

```kotlin
findByText(hint).assertIsNotHidden()
```