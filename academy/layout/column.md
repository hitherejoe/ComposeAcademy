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

When using the Column function there are four avialable properties that can be provided:

* **modifier** – the modifier to be applied to the composable
* **verticalArrangement** – the arrangement to be applied on the vertical axis
* **horizontalGravity** – the gravity to be applied on the horizontal axis
* **children** – the child composables to be displayed inside of the Column
  * required

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

At the minimum, we can provide child composables to be displayed inside of the column:

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

Setting the gravity on the column will set the positioning of the children on the horizontal axis

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

Setting the arrangement on the column will set the positioning of the children on the vertical axis

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
