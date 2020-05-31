---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Slider
description: Select a value from a range using a sliding component
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/slider.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

There is a single conctructor available to create a Scaffold composable

```kotlin
@Composable
fun Slider(
    value: Float,
    onValueChange: (Float) -> Unit,
    modifier: Modifier = Modifier,
    valueRange: ClosedFloatingPointRange<Float> = 0f..1f,
    @IntRange(from = 0) steps: Int = 0,
    onValueChangeEnd: () -> Unit = {},
    color: Color = MaterialTheme.colors.primary
)
```

* **value** – current selected value for the slider
  * required

* **onValueChange** – callback triggered whenever the selected value changes. E.g everytime a value is selected whilst the slider is being interacted with
  * required

* **modifier** – modifier to be applued to the slider

* **valueRange** – range of values used to make up the values of the slider

* **onValueChangeEnd** – callback triggered when value selection has completed. E.g the slider is not being dragged, with the value representing the final state of the slide

* **color** – the color to be used for the slider

## Examples

### Minimal slider
  
```kotlin
val state = state { 0f }
Column(horizontalGravity = Alignment.CenterHorizontally) {
    Text(text = state.value.toString())
    Slider(
        value = state.value,
        onValueChange = {
            state.value = it
        }
    )
}
```

### Ranged slider
  
```kotlin
val state = state { 0f }
Column(horizontalGravity = Alignment.CenterHorizontally) {
    Text(text = state.value.toString())
    Slider(
        value = state.value,
        onValueChange = {
            state.value = it
        },
        valueRange = 0f..5f
    )
}
```

### Stepped slider

```kotlin
val state = state { 0f }
Column(horizontalGravity = Alignment.CenterHorizontally) {
    Text(text = state.value.toString())
    Slider(
        value = state.value,
        onValueChange = {
            state.value = it
        },
        steps = 3
    )
}
```

### Colored slider

```kotlin
val state = state { 0f }
Column(horizontalGravity = Alignment.CenterHorizontally) {
    Text(text = state.value.toString())
    Slider(
        value = state.value,
        onValueChange = {
            state.value = it
        },
        color = Color.Red
    )
}
```

### Slider with listener

```kotlin
val state = state { 0f }
val endState = state { 0f }
Column(horizontalGravity = Alignment.CenterHorizontally) {
    Text(text = endState.value.toString())
    Slider(
        value = state.value,
        onValueChange = {
            state.value = it
        },
        onValueChangeEnd = {
            endState.value = state.value
        },
        color = Color.Red
    )
}
```

