---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Floating Action Button
description: Display a button in the form of a Floating Action Button
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/floatingActionButton.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun FloatingActionButton(
    onClick: () -> Unit,
    modifier: Modifier = Modifier,
    shape: Shape = MaterialTheme.shapes.small.copy(CornerSize(percent = 50)),
    backgroundColor: Color = MaterialTheme.colors.secondary,
    contentColor: Color = contentColorFor(backgroundColor),
    elevation: Dp = 6.dp,
    icon: @Composable () -> Unit
)
```

* **onClick** – callback used for when the button is clicked
  * required

* **modifier** – the modifier to be applied

* **shape** – the shape to be used for the background of the button

* **backgroundColor** – the color to be used for the background of the button

* **contentColor** – the color to be used for the content of the button

* **elevation** – the elevation to be applied to the button

* **icon** – the icon to be displayed on the button
  * required

## Examples

### Icon Floating Action Button
  
```kotlin
FloatingActionButton(onClick = {

}) {
    Icon(asset = Icons.Filled.Star)
}
```

![Floating Action Button](/academy/material/media/fab.png)

### Colored Floating Action Button
  
```kotlin
FloatingActionButton(
    onClick = {

    },
    backgroundColor = Color.Red,
    contentColor = Color.White
) {
    Icon(asset = Icons.Filled.Star)
}
```

![Floating Action Button](/academy/material/media/fab_colored.png)

### Elevated Floating Action Button

```kotlin
FloatingActionButton(
    onClick = {

    },
    elevation = 20.dp
) {
    Icon(asset = Icons.Filled.Star)
}
```

![Floating Action Button](/academy/material/media/fab_elevated.png)

### Shape Floating Action Button

```kotlin
FloatingActionButton(
    onClick = {

    },
    shape = RectangleShape
) {
    Icon(asset = Icons.Filled.Star)
}
```

![Floating Action Button](/academy/material/media/fab_shape.png)
