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

## Constructors

```kotlin
@Composable
fun Row(
    modifier: Modifier = Modifier,
    horizontalArrangement: Arrangement.Horizontal = Arrangement.Start,
    verticalGravity: Alignment.Vertical = Alignment.Top,
    children: @Composable() RowScope.() -> Unit
)
```

* **modifier** – the modifier to be applied to the composable

* **horizontalArrangement** – the arrangement to be applied on the horizontal axis

* **verticalGravity** – the gravity to be applied on the vertical axis

* **children** – the child composables to be displayed inside of the Column
  * required

## Examples

### Minimal row

At the minimum, we can provide child composables to be displayed inside of the row:

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

### Row with gravity

Setting the gravity on the row will set the positioning of the children on the vertical axis

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

### Row with arrangement

Setting the arrangement on the row will set the positioning of the children on the horizontal axis

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
