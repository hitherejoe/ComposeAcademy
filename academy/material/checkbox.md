---
# Page settings
layout: default
keywords:
comments: false
description: Checkboxes are crucial components when it comes to common areas of our applications. Be it settings screens, forms or any kind of content that needs to allow the user to toggle the checked state of the component – the Checkbox is essential in these scenarios. When it comes to this component, the Jetpack Compose provides a minimalistic approach to implementing this component within our UI.

# Micro navigation
micro_nav: true

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

We can see above that there are five available properties that we can pass to the Checkbox function:

* **checked** – whether or not the checkbox is currently checked. This is required
* **onCheckedChange** – a callback that will receive change events for when the checkbox selected state changes. Whilst this is required, null can be passed as a value
* **modifier** – the modifier(s) to be applied to the checkbox
* **color** – the color to be used for the checkbox. If not provided, then the secondary color from the application theme will be applied

## Simple checkbox

With the above in mind we can created a simple checkbox by providing the two required values for checked and onCheckedChange.

```kotlin
Checkbox(
    checked = false,
    onCheckedChange = { }
)
```

## Handling check changes


## Styled checkbox

```kotlin
Checkbox(
    checked = false,
    onCheckedChange = { },
    color = Color.Red
)
```


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
