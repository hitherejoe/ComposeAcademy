---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Scaffold
description: Construct a material design layout structure
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/scaffold.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

There is a single conctructor available to create a Scaffold composable

```kotlin
@Composable
fun Scaffold(
    scaffoldState: ScaffoldState = remember { ScaffoldState() },
    topAppBar: @Composable (() -> Unit)? = null,
    bottomAppBar: @Composable ((FabConfiguration?) -> Unit)? = null,
    floatingActionButton: @Composable (() -> Unit)? = null,
    floatingActionButtonPosition: FabPosition = FabPosition.End,
    drawerContent: @Composable (() -> Unit)? = null,
    bodyContent: @Composable (Modifier) -> Unit
)
```

* **scaffoldState** – current state of the scaffold (e.g drawer opened state)

* **topAppBar** – the top app bar to be displayed at the top of the scaffold

* **bottomAppBar** – the bottom app bar to be displayed at the bottom of the scaffold

* **floatingActionButton** – the floating action button to be displayed in the scaffold

* **floatingActionButtonPosition** – the positioning of the floating action button

* **drawerContent** – content to be displayed within the navigation drawer

* **bodyContent** – main body content to be displayed within the scaffold
  * required

## Examples

### Scaffold with Floating Action Button
  
```kotlin
val state = state { 0 }

val positions = listOf(
    Scaffold.FabPosition.End,
    Scaffold.FabPosition.Center
)

Scaffold(floatingActionButton = {
    FloatingActionButton(onClick = {
        if (state.value < positions.count() - 1) {
            state.value = state.value + 1
        } else {
            state.value = 0
        }
    }) {
        Icon(asset = Icons.Filled.Done)
    }
}, floatingActionButtonPosition = positions[state.value],
    bodyContent = {
        bodyContent()
    })
```

### Scaffold with docked Floating Action Button
  
```kotlin
val state = state { 0 }

val positions = listOf(
    Scaffold.FabPosition.EndDocked,
    Scaffold.FabPosition.CenterDocked
)

Scaffold(floatingActionButton = {
    FloatingActionButton(onClick = {
        if (state.value < positions.count() - 1) {
            state.value = state.value + 1
        } else {
            state.value = 0
        }
    }) {
        Icon(asset = Icons.Filled.Done)
    }
}, bottomAppBar = {
    BottomAppBar {

    }
}, floatingActionButtonPosition = positions[state.value],
    bodyContent = {
        bodyContent()
    })
```

### Scaffold with Top App Bar

```kotlin
Scaffold(topAppBar = {
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
}, bodyContent = {
    bodyContent()
})
```

### Scaffold with Drawer

```kotlin
val scaffoldState = remember { ScaffoldState() }
Scaffold(
    scaffoldState = scaffoldState,
    topAppBar = {
        TopAppBar(
            title = {
                Text(text = "Jetpack Compose")
            },
            navigationIcon = {
                IconButton(onClick = {
                    scaffoldState.drawerState = DrawerState.Opened
                }) {
                    Icon(Icons.Filled.Menu)
                }
            }
        )
    }, drawerContent = {
    Column(modifier = Modifier.fillMaxSize(),
        horizontalGravity = Alignment.CenterHorizontally) {
        Spacer(modifier = Modifier.preferredHeight(24.dp))
        Button(onClick = {
            scaffoldState.drawerState = DrawerState.Closed
        }) {
            Text(text = "Close Drawer")
        }
    }
}, bodyContent = {
    bodyContent()
})
```