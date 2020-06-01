---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Swipe Action
description: Perform swipe related actions on a component

# Micro navigation
micro_nav: false

---

## Swipe up

```kotlin
findByTag("MyTag").doGesture {
    sendSwipeUp()
}
```

## Swipe down

```kotlin
findByTag("MyTag").doGesture {
    sendSwipeDown()
}
```

## Swipe left

```kotlin
findByTag("MyTag").doGesture {
    sendSwipeLeft()
}
```

## Swipe right

```kotlin
findByTag("MyTag").doGesture {
    sendSwipeRight()
}
```