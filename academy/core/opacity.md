---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Opacity
description: A modifier used for applying opacity to a composable

# Micro navigation
micro_nav: false

---

## Opacity Function

```kotlin
Modifier.drawOpacity(0.2f)
```

You can apply opacity to a compasable by applying the opacity modifier. When applying  
the opacity modifier you will need to provide a Float Range from between 0.0 to 1.0 to  
reflect the opacity state of the composable.

## Example

```kotlin
Box(
    modifier = Modifier.preferredSize(100.dp, 100.dp).drawOpacity(0.2f),
    backgroundColor = Color.Green
)
```

![Opacity](/academy/core/media/opacity.png)
