---
# Page settings
layout: default
keywords:
comments: false
title: Tri-state Checkbox
description: 

# Micro navigation
micro_nav: false

---

## Constructor

There is a single constructor available for creating a  
new reference to a Tri-state Checkbox:

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

## Declaring a Tri-state checkbox

There are five available properties that we can pass to  
the Tri-state checkbox function:

* **state** – whether or not the checkbox is currently checked. 
This is required
* **onClick** – a callback that will receive change events for when  
the checkbox selected state changes. 
  * This is required
* **enabled** – whether or not the component is currently enabled for interaction
* **modifier** – the modifier(s) to be applied to the checkbox
* **color** – the color to be used for the checkbox. If not provided,  
then the secondary color from the application theme will be applied

## Toggle state

```kotlin
enum class ToggleableState {
    On,
    Off,
    Indeterminate
}
```

## Basic tri-state checkbox

```kotlin
TriStateCheckbox(
    state = ToggleableState.Indeterminate,
    onClick = { }
)
```
![](/academy/material/media/tristate_checkbox_indeterminate.png)

```kotlin
TriStateCheckbox(
    state = ToggleableState.On,
    onClick = { }
)
```
![](/academy/material/media/tristate_checkbox_on.png)

```kotlin
TriStateCheckbox(
    state = ToggleableState.Off,
    onClick = { }
)
```
![](/academy/material/media/tristate_checkbox_off.png)

## Colored checkbox

```kotlin
TriStateCheckbox(
    ...
    color = Color.Red
)
```
![](/academy/material/media/tristate_checkbox_colored.png)

## Handling check state

```kotlin
@Model
class TriStateFormState(var optionChecked: ToggleableState = 
    ToggleableState.Indeterminate)

@Composable
fun TriStateCheckboxComponent(formState: TriStateFormState) {
    TriStateCheckbox(
        state = formState.optionChecked,
        onClick = {
            when (formState.optionChecked) {
                ToggleableState.Off -> formState.optionChecked = 
                    ToggleableState.Indeterminate
                ToggleableState.On -> formState.optionChecked = 
                    ToggleableState.Off
                ToggleableState.Indeterminate -> formState.optionChecked = 
                    ToggleableState.On
            }
        }
    )
}
```
