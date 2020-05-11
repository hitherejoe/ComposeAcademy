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

# Detecting tap gestures

```kotlin
Text(
    text = "Tap me!",
    modifier = Modifier.padding(16.dp).tapGestureFilter(onTap = {
        // handle tap
    })
)
```

## Detecting double-tap gestures

```kotlin
Text(
    text = "Double tap me!",
    modifier = Modifier.padding(16.dp).doubleTapGestureFilter(onDoubleTap = {
        // handle double tap
    })
)
```

## Detecting long-press gestures

```kotlin
Text(
    text = "Long-press me!",
    modifier = Modifier.padding(16.dp).longPressGestureFilter(onLongPress = {
        // handle long-press
    })
)
```

## Detecting drag gestures

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
