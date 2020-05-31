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

## Constructor

There is a single constructor available to create a linear progress composable

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

### Assigned Value Progress Indicator
  
```kotlin
LinearProgressIndicator(progress = 0.5f)
```


### Colored Progress Indicator

```kotlin
LinearProgressIndicator(color = Color.Cyan)
```