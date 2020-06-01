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

![Circular Progress](/academy/material/media/progress_circular.png)

### Assigned Value Progress Indicator
  
```kotlin
CircularProgressIndicator(progress = 0.5f)
```

![Manual Circular Progress](/academy/material/media/progress_circular_manual.png)

### Colored Progress Indicator

```kotlin
CircularProgressIndicator(color = Color.Cyan)
```

![Colored Circular Progerss](/academy/material/media/progress_circular_colored.png)
