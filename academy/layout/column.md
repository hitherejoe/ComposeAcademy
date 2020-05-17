---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Column
description: A layout composable that lays out its child components in a vertical format.

# Micro navigation
micro_nav: false

---

## Constructor

```kotlin
@Composable
fun Column(
    modifier: Modifier = Modifier,
    verticalArrangement: Arrangement.Vertical = Arrangement.Top,
    horizontalGravity: Alignment.Horizontal = Alignment.Start,
    children: @Composable() ColumnScope.() -> Unit
)
```

## Minimal column

```kotlin
Column {
    Text(
        text = "First item",
        modifier = Modifier.padding(16.dp)
    )
    Text(
        text = "Second item",
        modifier = Modifier.padding(16.dp)
    )
    Text(
        text = "Third item",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Column](/academy/layout/media/column.png)

## Column with gravity

```kotlin
Column(
    modifier = Modifier.fillMaxSize(),
    horizontalGravity = Alignment.CenterHorizontally
) {
    Text(
        text = "First item",
        modifier = Modifier.padding(16.dp)
    )
    Text(
        text = "Second item",
        modifier = Modifier.padding(16.dp)
    )
    Text(
        text = "Third item",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Column with gravity](/academy/layout/media/column_gravity.png)

## Column with arrangement

```kotlin
Column(
    modifier = Modifier.fillMaxSize(),
    verticalArrangement = Arrangement.SpaceEvenly,
    horizontalGravity = Alignment.CenterHorizontally
) {
    Text(
        text = "First item",
        modifier = Modifier.padding(16.dp)
    )
    Text(
        text = "Second item",
        modifier = Modifier.padding(16.dp)
    )
    Text(
        text = "Third item",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Column with arrangement](/academy/layout/media/column_arrangement.png)
