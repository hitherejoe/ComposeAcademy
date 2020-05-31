---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Bottom Navigation
description: Display navigation at the bottom of the screen
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/bottomNavigation.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

There is a single conctructor available to create a Bottom Navigation composable

```kotlin
@Composable
fun BottomNavigation(
    modifier: Modifier = Modifier,
    backgroundColor: Color = MaterialTheme.colors.primarySurface,
    contentColor: Color = contentColorFor(backgroundColor),
    elevation: Dp = BottomNavigationElevation,
    content: @Composable RowScope.() -> Unit
) {
    Surface(
        color = backgroundColor,
        contentColor = contentColor,
        elevation = elevation,
        modifier = modifier
    ) {
        Row(
            Modifier.fillMaxWidth().preferredHeight(BottomNavigationHeight),
            horizontalArrangement = Arrangement.SpaceBetween,
            children = content
        )
    }
}
```

* **modifier** – modifier to be applied

* **content** – the content to be displayed inside of the bottom app bar
  * required

* **backgroundColor** – the background color to be applied

* **contentColor** – the color to be applied to the content inside the composable

* **fabConfiguration** – the positioning of the FAB

* **cutoutShape** – the shape to cutout for the placement of the FAB

```kotlin
@Composable
fun BottomNavigationItem(
    icon: @Composable () -> Unit,
    text: @Composable () -> Unit = emptyContent(),
    selected: Boolean,
    onSelected: () -> Unit,
    modifier: Modifier = Modifier,
    alwaysShowLabels: Boolean = true,
    activeColor: Color = contentColor(),
    inactiveColor: Color = EmphasisAmbient.current.medium.applyEmphasis(activeColor)
)
```

* **modifier** – modifier to be applied

* **content** – the content to be displayed inside of the bottom app bar
  * required

* **backgroundColor** – the background color to be applied

* **contentColor** – the color to be applied to the content inside the composable

* **fabConfiguration** – the positioning of the FAB

* **cutoutShape** – the shape to cutout for the placement of the FAB

### Minimal Bottom App Bar
  
```kotlin
val selectedItem = state { 0 }
val items = listOf(
    NavigationItem("Call", Icons.Filled.Call),
    NavigationItem("People", Icons.Filled.Face),
    NavigationItem("Email", Icons.Filled.Email)
)
Column {
    bodyContent()
    Spacer(modifier = Modifier.preferredHeight(64.dp))
    BottomNavigation {
        items.forEachIndexed { index, item ->
            BottomNavigationItem(
                icon = { Icon(item.icon) },
                text = { Text(text = item.label) },
                selected = selectedItem.value == index,
                onSelected = { selectedItem.value = index }
            )
        }
    }
}
```

### Styled Bottom App Bar
  
```kotlin
val selectedItem = state { 0 }
val items = listOf(
    NavigationItem("Call", Icons.Filled.Call),
    NavigationItem("People", Icons.Filled.Face),
    NavigationItem("Email", Icons.Filled.Email)
)
Column {
    bodyContent()
    Spacer(modifier = Modifier.preferredHeight(64.dp))
    BottomNavigation {
        items.forEachIndexed { index, item ->
            BottomNavigationItem(
                icon = { Icon(item.icon) },
                text = { Text(text = item.label) },
                selected = selectedItem.value == index,
                onSelected = { selectedItem.value = index },
                alwaysShowLabels = false
            )
        }
    }
}
```


### Bottom App Bar with FAB

```kotlin
val selectedItem = state { 0 }
val items = listOf(
    NavigationItem("Call", Icons.Filled.Call),
    NavigationItem("People", Icons.Filled.Face),
    NavigationItem("Email", Icons.Filled.Email)
)
Column {
    bodyContent()
    Spacer(modifier = Modifier.preferredHeight(64.dp))
    BottomNavigation {
        items.forEachIndexed { index, item ->
            BottomNavigationItem(
                icon = { Icon(item.icon) },
                text = { Text(text = item.label) },
                selected = selectedItem.value == index,
                onSelected = { selectedItem.value = index },
                activeColor = Color.Green,
                inactiveColor = Color.Red
            )
        }
    }
}
```