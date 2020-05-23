---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Border
description: Used to apply a border to the specified composable

# Micro navigation
micro_nav: false

---

## Constructor

There are two ways to create a new reference to a Border. The first is via the Border function:

```kotlin
fun Border(size: Dp, color: Color) = Border(size, SolidColor(color))
```

The second by directly instantiating the Border class.

```kotlin
@Immutable
data class Border(val size: Dp, val brush: Brush)
```

## Using the Border Function

When calling the Border function we are required to pass two properties:

* **size** – the thickness of the border
  * required
* **color** – the Color to be used for the border
  * required
  
```kotlin
Box(
    backgroundColor = Color.LightGray,
    border = Border(2.dp, Color.Black)
)
```

![Border](/academy/foundation/media/border.png)

## Using the Border Class
    
When using the Border class directly we are required to pass two properties:

* **size** – the thickness of the border
  * required
* **brush** – a reference to a Brush instance, used for the styling of the border
  * required

```kotlin
Box(
    backgroundColor = Color.LightGray,
    border = Border(2.dp, SolidColor(Color.Red))
)
```

![Border using brush](/academy/foundation/media/border_brush.png)
