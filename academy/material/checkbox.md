---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Checkbox
description: Checkboxes are crucial components when it comes to common areas of our applications. Be it settings screens, forms or any kind of content that needs to allow the user to toggle the checked state of the component – the Checkbox is essential in these scenarios. When it comes to this component, the Jetpack Compose provides a minimalistic approach to implementing this component within our UI.

# Micro navigation
micro_nav: false

---

# Constructor

There is a single constructor available for creating a new reference to a Checkbox component:

```kotlin
@Composable
fun Checkbox(
    checked: Boolean,
    onCheckedChange: ((Boolean) -> Unit)?,
    enabled: Boolean = true,
    modifier: Modifier = Modifier.None,
    color: Color = (+MaterialTheme.colors()).secondary
)
```

# Declaring a Checkbox

There are five available properties that we can pass to the Checkbox function:

* **checked** – whether or not the checkbox is currently checked
    * required
* **onCheckedChange** – a callback that will receive change events for when the checkbox selected state changes
    * required
* **modifier** – the modifier(s) to be applied to the checkbox
* **color** – the color to be used for the checkbox. If not provided, then the secondary color from the application theme will be applied

## Simple checkbox

```kotlin
Checkbox(
    checked = false,
    onCheckedChange = { }
)
```
<p align="center">
  <img src="/academy/material/media/checkbox.png">
</p>

## Handling check changes


## Styled checkbox

```kotlin
Checkbox(
    checked = false,
    onCheckedChange = { },
    color = Color.Red
)
```
<p align="center">
  <img src="/academy/material/media/colored_checkbox.png">
</p>

## Enabling / Disabling the checkbox

To enabled / disable the checkbox for user interactions, we can use the **enabled** property.

```kotlin
@Composable
fun CheckboxComponent(formState: FormState) {
    Checkbox(
        checked = formState.optionChecked,
        onCheckedChange = { },
        enabled = formState.enabled
    )
}
```

## Checkbox with label


```kotlin
@Composable
fun CheckboxWithLabel(formState: FormState) {
    Clickable(onClick = {
        formState.optionChecked = !formState.optionChecked
    }) {
        Row {
            Checkbox(
                checked = formState.optionChecked,
                onCheckedChange = { checked ->
                    formState.optionChecked = checked
                }
            )
            Text(
                text = "Notify me of updates",
                modifier = Modifier.padding(start = 8.dp)
            )
        }
    }
}
```
