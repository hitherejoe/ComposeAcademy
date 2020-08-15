---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Keyframe
description: Transition between states whilst animating values at specific frames
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


For this transiton, the physics animation builder will be used. This builder allows us to set pairs that consist of both the value for the animation and the timestamp at when that value should be reached.

```kotlin
someState using keyframes<Float> {
    50f at 200
    60f at 2200
    175f at 2500
}
```

The physics builder extends from the DurationBasedAnimation builder, meaning that we can set additional properties on our animation. These two properties are the duration and delay.

```kotlin
someState using keyframes<Float> {
    50f at 200
    60f at 2200
    175f at 2500
    duration = 2000
    delay = 200
}
```

## Examples

```kotlin
val sizeState = FloatPropKey()
val toState = state { "A" }

val transition = transitionDefinition {
    state("A") { this[sizeState] = 50f }
    state("B") { this[sizeState] = 175f }

    transition(fromState = CircleStatus.Shrinking, toState = CircleStatus.Growing) {
        sizeState using keyframes<Float> {
            duration = 2500
            50f at 200
            60f at 2200
            175f at 2500
        }
    }
    transition(fromState = CircleStatus.Growing, toState = CircleStatus.Shrinking) {
        sizeState using keyframes<Float> {
            duration = 2500
            175f at 200
            160f at 300
            100f at 750
            80f at 700
            50f at 500
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
