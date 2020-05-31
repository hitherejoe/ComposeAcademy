---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Stack
description: A layout composable that lays out its child components in a relative format, it's main use is for drawing children that require overlap. For this overlap, the z-index is defined by the order in which the components are declared

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
fun Stack(
    modifier: Modifier = Modifier,
    children: @Composable() StackScope.() -> Unit
)
```

## Scope

```kotlin
@LayoutScopeMarker
class StackScope {

    fun Modifier.gravity(align: Alignment) = this + StackGravityModifier(align)

    fun Modifier.matchParentSize() = this + StretchGravityModifier
}
```

## Examples

### Stack with relative children

```kotlin
Stack(modifier = Modifier.fillMaxSize()) {
    Text(
        text = ("Top!"),
        modifier = Modifier.gravity(Alignment.TopCenter).padding(16.dp)
    )
    
    Text(
        text = ("Left!"),
        modifier = Modifier.gravity(Alignment.CenterStart).padding(16.dp)
    )

    Text(
        text = ("Right!"),
        modifier = Modifier.gravity(Alignment.CenterEnd).padding(16.dp)
    )

    Text(
        text = ("Bottom!"),
        modifier = Modifier.gravity(Alignment.BottomCenter).padding(16.dp)
    )
}
```

![Stack with relative children](/academy/layout/media/stack_children.png)

### Stack with overlapping children

```kotlin
Stack(modifier = Modifier.fillMaxSize()) {
    Box(
        backgroundColor = Color.LightGray,
        modifier = Modifier.matchParentSize()
    )

    Text(
        text = ("Top!"),
        modifier = Modifier.gravity(Alignment.TopCenter).padding(16.dp)
    )
    
    Text(
        text = ("Left!"),
        modifier = Modifier.gravity(Alignment.CenterStart).padding(16.dp)
    )

    Text(
        text = ("Right!"),
        modifier = Modifier.gravity(Alignment.CenterEnd).padding(16.dp)
    )

    Text(
        text = ("Bottom!"),
        modifier = Modifier.gravity(Alignment.BottomCenter).padding(16.dp)
    )
}
```

![Stack with overlapping children](/academy/layout/media/stack_overlap.png)
