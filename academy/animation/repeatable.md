---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Repeatable
description: Transition between states and repeat the animation
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/animation/transitionAnimationDemos.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

When creating a repeatable transition there are three properties which can be provided:

* **fromState** – the state that is being animated from
* **toState** – the state that is being animated to
* **init** – the specification used to define our transition

```kotlin
fun transition(fromState: T? = null, toState: T? = null, init: TransitionSpec<T>.() -> Unit) {
    transition(fromState to toState, init = init)
}
```

For this transiton, the repeatable animation builder will be used. This builder allows us to set the two properties: 

* **iterations** – the number of iterations that should occur for the animation
* **animation** – the animation to be used for the transition

```kotlin
sizeState using repeatable<Float> {
    iterations = Infinite
    animation = tween {
        easing = LinearEasing
        duration = 1000
    }
}
```

## Example repeatable animation

```kotlin
val sizeState = FloatPropKey()
val toState = state { "A" }

val transition = transitionDefinition {
    state("A") { this[sizeState] = 50f }
    state("B") { this[sizeState] = 175f }

    transition(fromState = "A", toState = "B") {
        sizeState using repeatable<Float> {
            iterations = Infinite
            animation = tween {
                easing = LinearEasing
                duration = 1000
            }
        }
    }
    transition(fromState = "B", toState = "A") {
        sizeState using repeatable<Float> {
            iterations = Infinite
            animation = tween {
                easing = LinearEasing
                duration = 1000
            }
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
