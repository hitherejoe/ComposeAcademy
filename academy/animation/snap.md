---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Snap
description: Transition between states using a snap animation
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/animation/transitionAnimationDemos.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

When creating a snap transition there are two properties which can be provided:

* **fromToPairs** – the pairs of states used for the transition
  * required
* **nextState** – the next state which should be switched to once the animation has completed

```kotlin
fun snapTransition(vararg fromToPairs: Pair<T?, T?>, nextState: T? = null)
```

## Example snap animation

```kotlin
val sizeState = FloatPropKey()
val toState = state { "A" }

val transition = transitionDefinition {
    state("A") { this[sizeState] = 50f }
    state("B") { this[sizeState] = 175f }

    snapTransition("A" to "B")
    snapTransition("B" to "A")
}

Transition(
    definition = transition,
    toState = toState.value
) { state ->
    Canvas(modifier = Modifier.preferredSize(80.dp)) {
        drawCircle(Color.Red, state[sizeState])
    }
}

Button(onClick = {
    if (toState.value == "A") {
        toState.value = "B"
    } else {
        toState.value = "A"
    }
}, modifier = Modifier.padding(16.dp)) {
    Text("Animate!")
}
```
