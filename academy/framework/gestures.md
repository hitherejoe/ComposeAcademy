---
# Page settings
layout: default
keywords:
comments: false
title: Gestures
description: Gestures provide a way for us to detect interactions with components in our UI. These modifiers can be added to any of the components we declare, with their calback being triggered whenever the gesture event occurs.

# Micro navigation
micro_nav: false

---

## Detecting gestures

When it comes to detecting gestures, we need to add filter modifiers to the components that we wish to listen for interactions with. These filters will then receive events within their callbacks when the interactions occur.

### Tap gestures

```kotlin
Text(
    text = "Tap me!",
    modifier = Modifier.padding(16.dp).tapGestureFilter(onTap = {
        // handle tap
    })
)
```

### Double-tap gestures

```kotlin
Text(
    text = "Double tap me!",
    modifier = Modifier.padding(16.dp).doubleTapGestureFilter(onDoubleTap = {
        // handle double tap
    })
)
```

### Long-press gestures

```kotlin
Text(
    text = "Long-press me!",
    modifier = Modifier.padding(16.dp).longPressGestureFilter(onLongPress = {
        // handle long-press
    })
)
```

### Drag gestures

```kotlin
Text(
    text = "Drag me!",
    modifier = Modifier.padding(16.dp).longPressDragGestureFilter(
        object : LongPressDragObserver {

            override fun onLongPress(pxPosition: PxPosition) {
                super.onLongPress(pxPosition)
            }

            override fun onDrag(dragDistance: PxPosition): PxPosition {
                return super.onDrag(dragDistance)
            }

            override fun onDragStart() {
                super.onDragStart()
            }

            override fun onCancel() {
                super.onCancel()
            }

            override fun onStop(velocity: PxPosition) {
                super.onStop(velocity)
            }
        }
    )
)
```
