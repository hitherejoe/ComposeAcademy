---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Row
description: A layout composable that lays out its child components in a horizontal format.

# Micro navigation
micro_nav: false

---

## Constructor

```kotlin
@Composable
fun Row(
    modifier: Modifier = Modifier,
    horizontalArrangement: Arrangement.Horizontal = Arrangement.Start,
    verticalGravity: Alignment.Vertical = Alignment.Top,
    children: @Composable() RowScope.() -> Unit
)
```

## Minimal row

```kotlin
Row {
    Text(
        text = "First item",
        modifier = Modifier.padding(4.dp)
    )
    Text(
        text = "Second item",
        modifier = Modifier.padding(4.dp)
    )
    Text(
        text = "Third item",
        modifier = Modifier.padding(4.dp)
    )
}
```

![Column](/academy/layout/media/row.png)

## Row with gravity

```kotlin
Row(
    modifier = Modifier.fillMaxSize().padding(32.dp),
    verticalGravity = Alignment.CenterVertically
) {
    Text(
        text = "First item",
        modifier = Modifier.padding(4.dp)
    )
    Text(
        text = "Second item",
        modifier = Modifier.padding(4.dp)
    )
    Text(
        text = "Third item",
        modifier = Modifier.padding(4.dp)
    )
}
```

![Row with gravity](/academy/layout/media/row_gravity.png)

## Row with arrangement

```kotlin
Row(
    modifier = Modifier.fillMaxSize().padding(32.dp),
    horizontalArrangement = Arrangement.SpaceEvenly,
    verticalGravity = Alignment.CenterVertically
) {
    Text(
        text = "First item",
        modifier = Modifier.padding(4.dp)
    )
    Text(
        text = "Second item",
        modifier = Modifier.padding(4.dp)
    )
    Text(
        text = "Third item",
        modifier = Modifier.padding(4.dp)
    )
}
```

![Row with arrangement](/academy/layout/media/row_arrangement.png)
