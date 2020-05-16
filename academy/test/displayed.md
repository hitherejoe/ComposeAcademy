---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Displayed
description: Assert whether or not a composable is displayed on screen

# Micro navigation
micro_nav: false

---

## Assert a composable is displayed

```kotlin
findByText(hint).assertIsDisplayed()
```

## Assert a composable is not displayed

```kotlin
findByText(hint).assertIsNotDisplayed()
```