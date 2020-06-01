---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Button
description: Display interactable actions in the form of a button. Used to provide a means of user input with a variety of display options
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/button.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun Button(
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    enabled: Boolean = true,
    elevation: Dp = 2.dp,
    disabledElevation: Dp = 0.dp,
    shape: Shape = MaterialTheme.shapes.small,
    border: Border? = null,
    backgroundColor: Color = MaterialTheme.colors.primary,
    disabledBackgroundColor: Color = Button.defaultDisabledBackgroundColor,
    contentColor: Color = contentColorFor(backgroundColor),
    disabledContentColor: Color = Button.defaultDisabledContentColor,
    padding: InnerPadding = Button.DefaultInnerPadding,
    text: @Composable () -> Unit
)
```

* **onClick** – callback triggered when the button is clicked
  * required

* **modifier** – modifier to be applied to the composable

* **enabled** – whether or not the button is currently enabled

* **elevation** – elevation to be applied to the button

* **disabledElevation** – elevation to be applied to the button when disabled

* **shape** – shape to be used for the background of the button

* **border** – border to be applied to the button

* **backgroundColor** – background color to be applied to the button

* **disabledBackgroundColor** – background color to be applied to the button when disabled

* **contentColor** – color to be used for the content of the button

* **disabledContentColor** – color to be used for the content of the button when disabled

* **padding** – padding to be applied to the button

* **text** – composable to be used for the content of the button
  * required

## Examples

### Minimal Button
  
```kotlin
Button(onClick = {

}) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/button.png)

### Button with Shape
  
```kotlin
Button(onClick = {

}, shape = CutCornerShape(12.dp)) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/button_shape.png)

### Button with Border

```kotlin
Button(onClick = {

}, border = Border(2.dp, Color.Red)) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/button_border.png)

### Disabled Button

```kotlin
val disabled = state { false }
Button(onClick = {
    disabled.value = true
}, backgroundColor = Color.Green, disabledBackgroundColor = Color.Red,
    elevation = 8.dp, disabledElevation = 0.dp, disabledContentColor = Color.DarkGray,
    contentColor = Color.White, enabled = !disabled.value) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/button_disabled.png)
