---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Divider
description: Display a seperator to divide content
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/divider.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

There is a single conctructor available to create a Divider composable

```kotlin
@Composable
fun Divider(
    modifier: Modifier = Modifier,
    color: Color = MaterialTheme.colors.onSurface.copy(alpha = DividerAlpha),
    thickness: Dp = 1.dp,
    startIndent: Dp = 0.dp
)
```

* **modifier** – modifier to be applied to the composable

* **color** – color to be used for the divider

* **thickness** – thickness to be used for the divider

* **startIndent** – indentation to be applied to the start of the divider

### Minimal Button
  
```kotlin
Divider(color = Color.Red)
```

### Button with Shape
  
```kotlin
Divider(thickness = 12.dp)
```

### Button with Border

```kotlin
Divider(startIndent = 12.dp)
```
