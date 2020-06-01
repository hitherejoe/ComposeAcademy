---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Alert Dialog
description: Display a pop-up alert dialog
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/card.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun Card(
    modifier: Modifier = Modifier,
    shape: Shape = MaterialTheme.shapes.medium,
    color: Color = MaterialTheme.colors.surface,
    contentColor: Color = contentColorFor(color),
    border: Border? = null,
    elevation: Dp = 1.dp,
    content: @Composable () -> Unit
)
```

* **modifier** – modifier to be applied

* **shape** – shaoe to be used for the card background

* **color** – color to be used for the card surface

* **contentColor** – color to be used for the card content

* **border** – border to be applied to the card

* **elevation** – elevation to be applied to the card

* **content** – content to be displayed within the card
  * required


## Examples

### Minimal Card
  
```kotlin
Card {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/card.png)

### Card with Multiple Children
  
```kotlin
Card {
    Column {
        Text(
            text = "Jetpack",
            modifier = Modifier.padding(16.dp)
        )
        Spacer(modifier = Modifier.preferredHeight(8.dp))
        Text(
            text = "Compose",
            modifier = Modifier.padding(16.dp)
        )
    }

}
```

![Alert dialog](/academy/material/media/card_children.png)

### Card with Shape Background
  
```kotlin
Card(
    shape = RoundedCornerShape(3.dp)
) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/card_shape.png)

### Card with Background Color
  
```kotlin
Card(
    color = Color.LightGray
) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/card_background.png)

### Card with Colored Content
  
```kotlin
Card(
    color = Color.Black,
    contentColor = Color.White
) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/card_colored_content.png)

### Card with Border
  
```kotlin
Card(
    border = Border(2.dp, Color.Black)
) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/card_border.png)

### Card with Elevation
  
```kotlin
Card(
    elevation = 12.dp
) {
    Text(
        text = "Jetpack Compose",
        modifier = Modifier.padding(16.dp)
    )
}
```

![Alert dialog](/academy/material/media/card_elevation.png)
