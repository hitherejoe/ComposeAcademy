---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Switch
description: A toggleable component in the form of an on/off switch
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/switch.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun Switch(
    checked: Boolean,
    onCheckedChange: (Boolean) -> Unit,
    enabled: Boolean = true,
    color: Color = MaterialTheme.colors.secondaryVariant
)
```

* **checked** – whether or not the switch is currently checked. This is required

* **onCheckedChanget** – a callback that will receive change events for  
when the selected state of the component changes  
changes.    
  * This is required

* **enabled** – declares whether the component is currently enabled

* **color** – the color to be used for the component. If not provided,  
then the secondary color from the application theme will be applied

## Examples

### Basic switch

```kotlin
Switch(
    checked = true,
    onCheckedChange = { }
)
```

```kotlin
Switch(
    checked = false,
    onCheckedChange = { }
)
```

### Colored switch

```kotlin
Switch(
    checked = false,
    onCheckedChange = { },
    color = Color.Red
)
```

### Handled checked state

```kotlin
@Composable
fun SwitchComponent() {
    val isChecked = state { false }
    Switch(
        checked = isChecked.value,
        onCheckedChange = { checked ->
            isChecked.value = checked
        }
    )
}
```
