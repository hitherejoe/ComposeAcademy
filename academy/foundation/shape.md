---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Shape
description: Create shapes to use as backgrounds for composables
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/foundation/shape.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

Shapes can be used to provide specifically shaped backgrounds for composables. There are a collection of ways in which these shapes can be customised.

## Cut Corner Shape

A cut corner shape cuts the corners based on the provided values. A CutCornerShape can be created by using on of the provided approaches defined below. 

### Corners with the same dimension

```kotlin
fun CutCornerShape(corner: CornerSize)

Box(
    shape = CutCornerShape(CornerSize(12.dp)),
    backgroundColor = Color.Blue
)

fun CutCornerShape(size: Dp)

Box(
    shape = CutCornerShape(12.dp),
    backgroundColor = Color.Blue
)

fun CutCornerShape(size: Float)

Box(
    shape = CutCornerShape(12f),
    backgroundColor = Color.Blue
)

fun CutCornerShape(percent: Int)

Box(
    shape = CutCornerShape(12.dp),
    backgroundColor = Color.Blue
)
```

![Border](/academy/foundation/media/cut_corner_shape.png)

### Corners with different dimensions

```kotlin
fun CutCornerShape(
    topLeft: Dp = 0.dp,
    topRight: Dp = 0.dp,
    bottomRight: Dp = 0.dp,
    bottomLeft: Dp = 0.dp
)

Box(
    shape = CutCornerShape(12.dp, 4.dp, 12.dp, 4.dp),
    backgroundColor = Color.Blue
)

fun CutCornerShape(
    topLeft: Float = 0.0f,
    topRight: Float = 0.0f,
    bottomRight: Float = 0.0f,
    bottomLeft: Float = 0.0f
)

Box(
    shape = CutCornerShape(12f, 4f, 12f, 4f),
    backgroundColor = Color.Blue
)

fun CutCornerShape(
    @IntRange(from = 0, to = 50) topLeftPercent: Int = 0,
    @IntRange(from = 0, to = 50) topRightPercent: Int = 0,
    @IntRange(from = 0, to = 50) bottomRightPercent: Int = 0,
    @IntRange(from = 0, to = 50) bottomLeftPercent: Int = 0
)

Box(
    shape = CutCornerShape(40, 20, 50, 10),
    backgroundColor = Color.Blue
)
```

![Border](/academy/foundation/media/cut_corner_shape_dimensions.png)

## Rounded Corner Shape

A rounded corner shape rounds the corners based on the provided values. A RoundedCornerShape can be created by using on of the provided approaches defined below. 

### Corners with the same dimension

```kotlin
fun RoundedCornerShape(corner: CornerSize)

Box(
    shape = RoundedCornerShape(CornerSize(12.dp)),
    backgroundColor = Color.Blue
)

fun RoundedCornerShape(size: Dp)

Box(
    shape = RoundedCornerShape(12.dp),
    backgroundColor = Color.Blue
)

fun RoundedCornerShape(size: Float)

Box(
    shape = RoundedCornerShape(12f),
    backgroundColor = Color.Blue
)

fun RoundedCornerShape(percent: Int)

Box(
    shape = RoundedCornerShape(12.dp),
    backgroundColor = Color.Blue
)
```

![Border](/academy/foundation/media/rounded_corner_shape.png)

### Corners with different dimensions

```kotlin
fun RoundedCornerShape(
    topLeft: Dp = 0.dp,
    topRight: Dp = 0.dp,
    bottomRight: Dp = 0.dp,
    bottomLeft: Dp = 0.dp
)

Box(
    shape = RoundedCornerShape(12.dp, 4.dp, 12.dp, 4.dp),
    backgroundColor = Color.Blue
)

fun RoundedCornerShape(
    topLeft: Float = 0.0f,
    topRight: Float = 0.0f,
    bottomRight: Float = 0.0f,
    bottomLeft: Float = 0.0f
)

Box(
    shape = RoundedCornerShape(12f, 4f, 12f, 4f),
    backgroundColor = Color.Blue
)

fun RoundedCornerShape(
    @IntRange(from = 0, to = 50) topLeftPercent: Int = 0,
    @IntRange(from = 0, to = 50) topRightPercent: Int = 0,
    @IntRange(from = 0, to = 50) bottomRightPercent: Int = 0,
    @IntRange(from = 0, to = 50) bottomLeftPercent: Int = 0
)

Box(
    shape = RoundedCornerShape(40, 20, 50, 10),
    backgroundColor = Color.Blue
)
```

![Border](/academy/foundation/media/rounded_corner_shape_dimensions.png)


