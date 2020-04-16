---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: AndroidView
description: When it comes to building our UI in jetpack compose, for a lot of applications it will come at a time when our UIs are already build using a mixture of existing solutions - be it XML layouts or custom views. It may even be the case that we have custom views in our current Android project that aren’t quite ready to be converted over to compose just yet, or maybe it doesn’t feel very pragmatic to do so. Regardless which of the above is the case, there are solutions in side of the jetpack compose API that aim to help out in this area.

# Micro navigation
micro_nav: false

---

# Constructor

There is a single constructor available for creating a new reference to a AndroidView component:

```kotlin
@Composable
fun AndroidView(
    @LayoutRes resId: Int, 
    postInflationCallback: (View) -> Unit = { _ -> }
) {
    AndroidViewHolder(
        postInflationCallback = postInflationCallback,
        resId = resId
    )
}
```

# Declaring an AndroidView

There are two available properties that we can pass to the AndroidView function:

* **resId** – the id of the layout which we wish to inflate
    * required
* **postInflationCallback** – a callback for when the view has been inflated
    * required

## Building an AndroidView

```kotlin
AndroidView(resId = R.layout.view_demo)
```

## Using an AndroidView

```kotlin
Surface(
    modifier = Modifier.padding(16.dp),
    color = Color.White,
    shape = RoundedCornerShape(CornerSize(4.dp))
) {

    Column(modifier = Modifier.padding(16.dp)) {
        AndroidView(resId = R.layout.view_demo)
    }
}
```

<p align="center">
  <img src="/academy/foundation/media/androidview.png">
</p>

