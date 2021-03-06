---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Border
description: Apply a border to the specified composable
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/foundation/border.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

### Function

```kotlin
fun Border(size: Dp, color: Color) = Border(size, SolidColor(color))
```

* **size** – the thickness of the border
  * required

* **color** – the Color to be used for the border
  * required

### Class

```kotlin
@Immutable
data class Border(val size: Dp, val brush: Brush)
```

* **size** – the thickness of the border
  * required

* **brush** – a reference to a Brush instance, used for the styling of the border
  * required

## Examples

### Using the Border Function

When calling the Border function there are two required properties:
  
```kotlin
Box(
    backgroundColor = Color.LightGray,
    border = Border(2.dp, Color.Black)
)
```

![Border](/academy/foundation/media/border.png)

### Using the Border Class
    
When using the Border class directly there are two required properties:

```kotlin
Box(
    backgroundColor = Color.LightGray,
    border = Border(2.dp, SolidColor(Color.Red))
)
```

![Border using brush](/academy/foundation/media/border_brush.png)
