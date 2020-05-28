---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: AndroidView
description: Declare the use of Android views within composables
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/foundation/border.kt"
    external_url: true
    
# Micro navigation
micro_nav: false

---

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

When using the AndroidView function there are two required properties:

* **resId** – the id of the layout which we wish to inflate
  * required
* **postInflationCallback** – a callback for when the view has been inflated
  * required

### Building an AndroidView

```kotlin
AndroidView(resId = R.layout.view_demo)
```

### Using an AndroidView

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

![Android View](/academy/foundation/media/androidview.png)

### Embed custom views

```kotlin
Surface(
    modifier = Modifier.padding(16.dp),
    color = Color.White,
    shape = RoundedCornerShape(CornerSize(4.dp))
) {

    Column(modifier = Modifier.padding(16.dp)) {
        MyCustomView(context = ContextAmbient.current)
    }
}

class MyCustomView @JvmOverloads constructor(
    context: Context,
    attrs: AttributeSet? = null,
    defStyleAttr: Int = 0
) : AppCompatTextView(context, attrs, defStyleAttr) {

    init {
        layoutParams = 
            ViewGroup.LayoutParams(MATCH_PARENT, WRAP_CONTENT)
        text = "Hello there!"
    }

}
```
