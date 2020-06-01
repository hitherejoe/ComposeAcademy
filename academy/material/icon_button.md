---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Icon Button
description: Display a button with an icon for the content
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/iconButton.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun IconButton(
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    icon: @Composable () -> Unit
)
```

* **onClick** – callback used for when the button is clicked
  * required

* **modifier** – the modifier to be applied

* **icon** – the icon to be displayed on the button
  * required

## Examples

### Displaying an Icon Button
  
```kotlin
IconButton(onClick = {

}, icon = {
    Icon(asset = Icons.Default.Person)
})
```
