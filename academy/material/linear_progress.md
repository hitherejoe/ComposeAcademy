---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Linear Progress
description: Display a linear progress indicator
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
fun LinearProgressIndicator(
    modifier: Modifier = Modifier,
    color: Color = MaterialTheme.colors.primary
)
```

* **modifier** – modifier to be applied

* **color** – the color to be used for the indicator

## Examples

### Minimal Progress Indicator
  
```kotlin
LinearProgressIndicator()
```

![Circular Progress](/academy/material/media/linear_progress_one.png)

### Assigned Value Progress Indicator
  
```kotlin
LinearProgressIndicator(progress = 0.5f)
```

![Circular Progress](/academy/material/media/linear_progress_one.png)

### Colored Progress Indicator

```kotlin
LinearProgressIndicator(color = Color.Cyan)
```

![Circular Progress](/academy/material/media/linear_progress_two.png)
