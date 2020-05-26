---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Tween
description: Transition between states using a tween animation
# Micro navigation
micro_nav: false

---

## Construction

When creating a tween transition there are two properties which can be provided:

* **fromState** – the state that is being animated from
* **toState** – the state that is being animated to
* **init** – the specification used to define our transition

```kotlin
fun transition(fromState: T? = null, toState: T? = null, init: TransitionSpec<T>.() -> Unit) {
    transition(fromState to toState, init = init)
}
```

For this transiton, the tween animation builder will be used. This builder allows us to set the easing property - this is used to define the rate of change in which the values are animated.

```kotlin
sizeState using tween<Float> {
    easing = FastOutLinearInEasing
}
```

The tween builder extends from the DurationBasedAnimation builder, meaning that we can set additional properties on our animation. These two properties are the duration and delay.

```kotlin
sizeState using tween<Float> {
    easing = FastOutLinearInEasing
    duration = 2000
    delay = 200
}
```

## Example tween animation

```kotlin
val sizeState = FloatPropKey()
val toState = state { "A" }

val transition = transitionDefinition {
    state("A") { this[sizeState] = 50f }
    state("B") { this[sizeState] = 175f }

    transition(fromState = "A", toState = "B") {
        sizeState using tween<Float> {
            duration = 2000
            easing = FastOutLinearInEasing
        }
    }
    transition(fromState = "B", toState = "A") {
        sizeState using tween<Float> {
            duration = 2000
            easing = LinearOutSlowInEasing
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
