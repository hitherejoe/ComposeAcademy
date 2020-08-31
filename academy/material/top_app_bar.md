---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Top App Bar
description: Display an Application Bar with optional navigational components
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/topAppBar.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

### Contracted Content

```kotlin
@Composable
fun TopAppBar(
    title: @Composable () -> Unit,
    modifier: Modifier = Modifier,
    navigationIcon: @Composable (() -> Unit)? = null,
    actions: @Composable RowScope.() -> Unit = {},
    backgroundColor: Color = MaterialTheme.colors.primarySurface,
    contentColor: Color = contentColorFor(backgroundColor),
    elevation: Dp = TopAppBarElevation
)
```

* **title** – main title to be displayed within the top app bar
  * required

* **modifier** – modifier to be applied to the composable

* **navigationIcon** – navigation icon to be displayed at the start of the composable

* **actions** – actions to be displayed at the end of the disposable

* **backgroundColor** – background color to be used

* **contentColor** – color to be used for the content

* **elevation** – elevation to be applied

### Composed Content

```kotlin
@Composable
fun TopAppBar(
    modifier: Modifier = Modifier,
    backgroundColor: Color = MaterialTheme.colors.primarySurface,
    contentColor: Color = contentColorFor(backgroundColor),
    elevation: Dp = TopAppBarElevation,
    content: @Composable RowScope.() -> Unit
)
```

* **modifier** – modifier to be applied to the composable

* **backgroundColor** – background color to be used

* **contentColor** – color to be used for the content

* **elevation** – elevation to be applied

* **content** – content to be displayed

## Examples

### Minimal Top App Bar
  
```kotlin
TopAppBar(
    title = {
        Text(text = "Jetpack Compose")
    }
)
```

### Top App Bar with Icon
  
```kotlin
TopAppBar(
    title = {
        Text(text = "Jetpack Compose")
    },
    navigationIcon = {
        IconButton(onClick = { }) {
            Icon(Icons.Filled.ArrowBack)
        }
    }
)
```

### Styled Top App Bar

```kotlin
TopAppBar(
    title = {
        Text(text = "Jetpack Compose")
    },
    backgroundColor = Color.Black,
    contentColor = Color.White,
    elevation = 12.dp
)
```

### Top App Bar with Actions

```kotlin
TopAppBar(
    title = {
        Text(text = "Jetpack Compose")
    },
    actions = {
        Text(text = "Save", modifier = Modifier.padding(16.dp).clickable(onClick = {
            
        }, color = Color.White)
    }
)
```

