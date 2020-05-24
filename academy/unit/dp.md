---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Dp
description: A unit used to represent Display Pixel values

# Micro navigation
micro_nav: false

---

## Creating Display Pixel references

There are four ways in which you can construct a Dp reference:

```kotlin
val intAsDp = 8.dp
val floatAsDp = 8f.dp
val doubleAsDp = 8.5.dp
val constructor = Dp(8f)

val hairline = Dp.Hairline
val infinity = Dp.Infinity
val unspecified = Dp.Unspecified
```

## Display Pixel operations

```kotlin
val plus = 8.dp + 6.dp
val minus = 8.dp - 6.dp
val unaryMinus = 8.dp - (-8).dp
```

## Multiplication operations

```kotlin
val times = 8.dp * 6.dp
val timesFloat = 8.dp * 6f
val timesInt = 8.dp * 6
```

## Division operations

```kotlin
val divide = 8.dp / 6.dp
val divideFloat = 8.dp / 6f
val divideInt = 8.dp / 6
```

## Integer operations

```kotlin
val intTimes = 8 * 6.dp
val intDivide = 8 / 6.dp
```

## Float operations

```kotlin
val floatTimes = 8f * 6.dp
val floatDivide = 8f / 6.dp
```

## Double operations

```kotlin
val doubleTimes = 8.0 * 6.dp
val doubleDivide = 8.0 / 6.dp
```

## Min / Max calculations

```kotlin
val min = min(6.dp, 12.dp)
val max = max(6.dp, 12.dp)
```

## Min / Max calculations

```kotlin
val min = min(6.dp, 12.dp)
val max = max(6.dp, 12.dp)
```

## Utility functions

```kotlin
val coerceIn = 8.dp.coerceIn(6.dp, 12.dp)
val coerceAtLeast = 8.dp.coerceAtLeast(6.dp)
val coerceAtMost = 8.dp.coerceAtMost(6.dp)
val isFinite = 8.dp.isFinite()
```
