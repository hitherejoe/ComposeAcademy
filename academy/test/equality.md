---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Equality
description: Assert the equality of content within tests

# Micro navigation
micro_nav: false

---

## Assert labels are equal

```kotlin
findByTag(tag).assertLabelEquals(label)
```

## Assert values are equal

```kotlin
findByTag(tag).assertValueEquals(value)
```

## Assert semantic configurations are equal

```kotlin
findByTag(tag).assertSemanticsIsEqualTo(semanticsConfiguration)
```