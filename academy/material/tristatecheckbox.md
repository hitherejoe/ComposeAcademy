---
# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Tri-state Checkbox
description: Used for a toggleable state in the form of a check mark, with the addition of an intermediate checked state
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/triStateCheckbox.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructor

```kotlin
@Composable
fun TriStateCheckbox(
    state: ToggleableState,
    onClick: () -> Unit,
    enabled: Boolean = true,
    modifier: Modifier = Modifier.None,
    color: Color = MaterialTheme.colors.secondary
)
```

* **state** – whether or not the checkbox is currently checked. 
  * This is required

* **onClick** – a callback that will receive change events for when  
the checkbox selected state changes. 
  * This is required

* **enabled** – whether or not the component is currently enabled for interaction

* **modifier** – the modifier(s) to be applied to the checkbox

* **color** – the color to be used for the checkbox. If not provided,  
then the secondary color from the application theme will be applied

## Examples

### Toggle state

```kotlin
enum class ToggleableState {
    On,
    Off,
    Indeterminate
}
```

### Basic tri-state checkbox

```kotlin
TriStateCheckbox(
    state = ToggleableState.Indeterminate,
    onClick = { }
)
```

```kotlin
TriStateCheckbox(
    state = ToggleableState.On,
    onClick = { }
)
```

```kotlin
TriStateCheckbox(
    state = ToggleableState.Off,
    onClick = { }
)
```

### Colored checkbox

```kotlin
TriStateCheckbox(
    ...
    color = Color.Red
)
```

### Handling check state

```kotlin
@Composable
fun TriStateCheckboxComponent(formState: TriStateFormState) {
    val toggleState = state { ToggleableState.Indeterminate }
    TriStateCheckbox(
        state = toggleState.value,
        onClick = {
            when (toggleState.value) {
                ToggleableState.Off -> toggleState.value = 
                    ToggleableState.Indeterminate
                ToggleableState.On -> toggleState.value = 
                    ToggleableState.Off
                ToggleableState.Indeterminate -> toggleState.value = 
                    ToggleableState.On
            }
        }
    )
}
```
