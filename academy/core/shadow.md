---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Shadow
description: A modifier used for applying a shadow to a composable

# Micro navigation
micro_nav: false

---

## Draw Shadow Function

```kotlin
Modifier.drawShadow(12.dp, RectangleShape)
```

You can apply a shadow to a compasable by applying the shadow modifier. When applying the shadow modifier you will need to provide:

  * **elevation** - the elevation to be applied when drawing the shadow

  * **shape** - the shape to be applied when drawing the shadow

  * **clipToOutline** - whether or not the shadow should be clipped to the outline  
  of the shape

  * **opacity** - the opacity to be applied when drawing the shadow

## Example

```kotlin
Box(
    modifier = Modifier.preferredSize(100.dp, 100.dp).drawShadow(12.dp, RectangleShape),
    backgroundColor = Color.Green
)
```
