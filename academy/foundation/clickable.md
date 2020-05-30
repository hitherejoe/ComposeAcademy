---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Clickable
description: Listen for click events on composables
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/foundation/clickable.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

The clickable modifier can be used to listen for a variety of click evens on a composable.

```kotlin
@Composable
fun Modifier.clickable(
    enabled: Boolean = true,
    onClickLabel: String? = null,
    interactionState: InteractionState = remember { InteractionState() },
    indication: Indication? = IndicationAmbient.current(),
    onLongClick: (() -> Unit)? = null,
    onDoubleClick: (() -> Unit)? = null,
    onClick: () -> Unit
)
```

When using the Clickable modifier there are a collection of properties that can be provided:

* **enabled** – whether or not the click functionality is enabled
* **onClickLabel** – accessibility label for the click action
* **interactionState** – the interaction state of the composable, updated when pressed
* **indication** – state to be displayed when the composable is pressed
* **onLongClick** – a callback for when the composable is long clicked
* **onDoubleClick** – a callback for when the composable is double clicked
* **onClick** – a callback for when the composable is clicked
  * required

## Using the Clickable modifier
  
```kotlin
Text(
    text = "Clickable",
    modifier = Modifier.padding(16.dp).clickable(onClick = {

    }, onClickLabel = "Click to open document")
)
```

## Clickable listeners
  
```kotlin
Text(
    text = "Clickable",
    modifier = Modifier.padding(16.dp).clickable(onClick = {

    }, onLongClick = {

    }, onDoubleClick = {

    })
)
```
