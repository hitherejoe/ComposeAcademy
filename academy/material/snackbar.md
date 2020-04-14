---
# Page settings
layout: default
keywords:
comments: false
title: Snackbar
description: Snackbars provide us with a wya to show short, non-blocking alerts to the user. Usually displayed at the bottom of the screen, these components can also provide a single action for the user to take in the context of the given message.

# Micro navigation
micro_nav: true

---

# Constructor

There is a single constructor available for creating a new reference to a Snackbar:

```kotlin
@Composable
fun Snackbar(
    text: @Composable() () -> Unit,
    action: @Composable() (() -> Unit)? = null,
    modifier: Modifier = Modifier.None,
    actionOnNewLine: Boolean = false
)
```

# Declaring a Snackbar

There are four available properties that we can pass to the Checkbox function:

* **text** – the text to be displayed within the snackbar
    * required
* **action** – an action, in the form of a composable, to be displayed within the snackbar
* **modifier** – the modifier(s) to be applied to the snackbar
* **actionOnNewLine** – declares whether the action text should be displayed on a new line

## Minimal snackbar

```kotlin
Snackbar(
    text = { Text(text = "This is a snackbar!") }
)
```
<p align="center">
  <img src="/academy/material/media/snackbar.png">
</p>

## Handling actions

```kotlin
Snackbar(
    text = { Text(text = "This is a snackbar!") },
    action = {
        Clickable(onClick = {
            // Handle action
        }) {
            Text(
                text = "Undo",
                modifier = Modifier.padding(16.dp),
                style = TextStyle(
                    fontWeight = FontWeight.Bold,
                    color = snackbarPrimaryColorFor(MaterialTheme.colors)
                )
            )
        }
    }
)
```

<p align="center">
  <img src="/academy/material/media/snackbar_action.png">
</p>

## Action on new line

```kotlin
Snackbar(
    text = { Text(text = "This is a snackbar with a lot of text, that way it makes sense to use the new line!") },
    action = {
        Clickable(onClick = {
            // Handle action
        }) {
            Text(
                text = "Undo",
                modifier = Modifier.padding(16.dp),
                style = TextStyle(
                    fontWeight = FontWeight.Bold,
                    color = snackbarPrimaryColorFor(MaterialTheme.colors)
                )
            )
        }
    },
    actionOnNewLine = true
)
```

<p align="center">
  <img src="/academy/material/media/snackbar_new_line.png">
</p>
