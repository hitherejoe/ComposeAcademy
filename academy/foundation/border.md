---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Border
description: Used to draw a border of the given thickness and color around the view that it is being applied to

# Micro navigation
micro_nav: false

---

## Constructor

There are two ways to create a new reference to a Border. the first is via the Border function:

```kotlin
fun Border(size: Dp, color: Color) = Border(size, SolidColor(color))
```

The second by directly instantiating the Border class.

```kotlin
@Immutable
data class Border(val size: Dp, val brush: Brush)
```

## Declaring a Border

When calling the Border function we are required to pass two properties:

* **size** – the thickness of the border
    * required
* **color** – the Color to be used for the border
    * required
    
When using the Border class directly we are required to pass two properties:

* **size** – the thickness of the border
    * required
* **brush** – a reference to a Brush instance, used for the styling of the border
    * required

## Using a border

```kotlin
Box(
    backgroundColor = Color.LightGray,
    border = Border(2.dp, Color.Black)
)
```

![](/academy/foundation/media/border.png)

```kotlin
Box(
    backgroundColor = Color.LightGray,
    border = Border(2.dp, SolidColor(Color.Red))
)
```

![](/academy/foundation/media/border_brush.png)
