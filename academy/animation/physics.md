---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Physics
description: Transition between states using a physics based animation
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/animation/transitionAnimationDemos.kt"
    external_url: true
    
# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
fun transition(fromState: T? = null, toState: T? = null, init: TransitionSpec<T>.() -> Unit) {
    transition(fromState to toState, init = init)
}
```

* **fromState** – the state that is being animated from

* **toState** – the state that is being animated to

* **init** – the specification used to define our transition

For this transiton, the physics animation builder will be used. This builder allows us to set the two properties: 

* **stiffness** – the damping ratio of the spring used for the animation

* **dampingRatio** – the stiffness of the spring used for the animation

```kotlin
someState using physics<Float> {
    stiffness = 5f
    dampingRatio = 5f
}
```


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

val state = transition(
    definition = transition,
    toState = toState.value
)
Canvas(modifier = Modifier.preferredSize(80.dp)) {
    drawCircle(Color.Red, state[sizeState])
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
