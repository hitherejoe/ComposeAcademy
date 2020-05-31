---
# Page settings
layout: default
keywords:
comments: false
title: Switch
description: 

# Micro navigation
micro_nav: false

---

## Constructors

There is a single constructor available for creating a new reference to a Switch:

```kotlin
@Composable
fun Switch(
    checked: Boolean,
    onCheckedChange: (Boolean) -> Unit,
    enabled: Boolean = true,
    color: Color = MaterialTheme.colors.secondaryVariant
)
```

* **checkedt** – whether or not the switch is currently checked. This is required
* **onCheckedChanget** – a callback that will receive change events for  
when the selected state of the component changes  
changes.    
  * This is required
* **enabledt** – declares whether the component is currently enabled
* **colort** – the color to be used for the component. If not provided,  
then the secondary color from the application theme will be applied

## Examples

### Basic switch

```kotlin
Switch(
    checked = true,
    onCheckedChange = { }
)
```

![Checked switch](/academy/material/media/switch_checked.png)


```kotlin
Switch(
    checked = false,
    onCheckedChange = { }
)
```

![Unchecked switch](/academy/material/media/switch_unchecked.png)

### Colored switch

```kotlin
Switch(
    checked = false,
    onCheckedChange = { },
    color = Color.Red
)
```

![Colored switch](/academy/material/media/switch_colored.png)

### Handled checked state

```kotlin
@Model
class FormState(var optionChecked: Boolean = false)

@Composable
fun SwitchComponent(formState: FormState) {
    Switch(
        checked = formState.optionChecked,
        onCheckedChange = { checked ->
            formState.optionChecked = checked
        }
    )
}
```
