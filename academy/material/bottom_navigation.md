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

## Constructors

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

* **content** – content to be displayed inside of the navigation bar
  * required

* **backgroundColor** – color used for the background of the composable

* **contentColor** – the color to be applied to the content inside the composable

* **elevation** – elevation to be applied to the bar

## Examples

### Navigation Items

When it comes to creating a bottom navigation bar, we need to provide the items that we wish to display. This is done using the BottomNavigtionitem composable:

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

* **icon** – the icon to be displayed for the item

* **text** – the text to be displayed for the item
  * required

* **selected** – current selection state for the item
  * required

* **onSelected** – callback triggered when the item becomes selected
  * required

* **modifier** – modifier to be applied to the navigation item

* **alwaysShowLabels** – whether or not labels should always be shown for the item

* **activeColor** – color to be used for active content (e.g selected item)

* **inactiveColor** – color to be used for inactive content (e.g unselected item)

### Minimal Bottom Navigation
  
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

![Alert dialog](/academy/material/media/bottom_nav.png)

### Bottom Navigation without Labels
  
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

![Alert dialog](/academy/material/media/bottom_nav_labels.png)

###Styled Bottom Navigation

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

![Alert dialog](/academy/material/media/bottom_nav_styled.png)
