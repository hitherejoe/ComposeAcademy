---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Physics
description: Transition between states using a physics based animation
# Micro navigation
micro_nav: false

---

## Construction

When creating a repeatable transition there are three properties which can be provided:

* **fromState** – the state that is being animated from
* **toState** – the state that is being animated to
* **init** – the specification used to define our transition

```kotlin
fun transition(fromState: T? = null, toState: T? = null, init: TransitionSpec<T>.() -> Unit) {
    transition(fromState to toState, init = init)
}
```

For this transiton, the physics animation builder will be used. This builder allows us to set the two properties: 

* **stiffness** – the damping ratio of the spring used for the animation
* **dampingRatio** – the stiffness of the spring used for the animation

```kotlin
sizeState using physics<Float> {
    stiffness = 5f
    dampingRatio = 5f
}
```

## Example physics animation

```kotlin
val sizeState = FloatPropKey()
val toState = state { "A" }

val transition = transitionDefinition {
    state("A") { this[sizeState] = 50f }
    state("B") { this[sizeState] = 175f }

    transition(fromState = "A", toState = "B") {
        sizeState using physics<Float> {
            stiffness = 5f
            dampingRatio = 5f
        }
    }
    transition(fromState = "B", toState = "A") {
        sizeState using physics<Float> {
            stiffness = 5f
            dampingRatio = 5f
        }
    }
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
