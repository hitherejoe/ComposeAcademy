---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Circular Progress
description: Display a circular progress indicator
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/progress.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

There is a single conctructor available to create a circular progress composable

```kotlin
@Composable
fun CircularProgressIndicator(
    modifier: Modifier = Modifier,
    color: Color = MaterialTheme.colors.primary,
    strokeWidth: Dp = ProgressIndicatorConstants.DefaultStrokeWidth
)
```

* **modifier** – modifier to be applied

* **color** – the color to be used for the indicator

* **strokeWidth** – the width to be used for the indicator stroke

## Examples

### Minimal Progress Indicator
  
```kotlin
CircularProgressIndicator()
```

![Alert dialog](/academy/material/media/progress_circular.png)

### Assigned Value Progress Indicator
  
```kotlin
CircularProgressIndicator(progress = 0.5f)
```

![Alert dialog](/academy/material/media/progress_circular_manual.png)

### Colored Progress Indicator

```kotlin
CircularProgressIndicator(color = Color.Cyan)
```

![Alert dialog](/academy/material/media/progress_circular_colored.png)
