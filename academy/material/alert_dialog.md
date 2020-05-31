---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Alert Dialog
description: Display a pop-up alert dialog
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/alertDialog.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

There is a two conctructors available to create an Alert Dialog composable

```kotlin
@Composable
fun AlertDialog(
    onCloseRequest: () -> Unit,
    title: @Composable (() -> Unit)? = null,
    text: @Composable () -> Unit,
    confirmButton: @Composable () -> Unit,
    dismissButton: @Composable (() -> Unit)? = null,
    buttonLayout: AlertDialogButtonLayout = SideBySide,
    shape: Shape = MaterialTheme.shapes.medium
)
```

* **onCloseRequest** – the text to be displayed
  * required
* **text** – the text to be displayed
  * required
* **confirmButton** – the text to be displayed
  * required
* **title** – the modifier to be applied to the composable
* **dismissButton** – the Color to be used for the text
* **buttonLayout** – the font size to be applued
* **shape** – the font style to be applied

```kotlin
@Composable
fun AlertDialog(
    onCloseRequest: () -> Unit,
    title: (@Composable () -> Unit)? = null,
    text: @Composable () -> Unit,
    buttons: @Composable () -> Unit,
    shape: Shape = MaterialTheme.shapes.medium
)
```

* **onCloseRequest** – the text to be displayed
  * required
* **text** – the text to be displayed
  * required
* **buttons** – the text to be displayed
  * required
* **title** – the modifier to be applied to the composable
* **shape** – the Color to be used for the text

### Displaying a dialog
  
```kotlin
val showingDialog = state { false }
if (showingDialog.value) {
    AlertDialog(
        onCloseRequest = {
            showingDialog.value = false
        },
        text = {
            Text(text = "Body message")
        },
        title = {
            Text(text = "Title")
        },
        buttons = {
            Row(horizontalArrangement = Arrangement.End,
                modifier = Modifier.fillMaxWidth()
            ) {
                Text(text = "Close",
                    modifier = Modifier.padding(16.dp).clickable(onClick = {
                        showingDialog.value = false
                    }))
            }
        })
}
```
