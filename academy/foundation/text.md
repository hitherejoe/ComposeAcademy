---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Text
description: Create componenets composed of textual content
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/foundation/text.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

```kotlin
@Composable
fun Text(
    text: String,
    modifier: Modifier = Modifier,
    color: Color = Color.Unset,
    fontSize: TextUnit = TextUnit.Inherit,
    fontStyle: FontStyle? = null,
    fontFamily: FontFamily? = null,
    letterSpacing: TextUnit = TextUnit.Inherit,
    textDecoration: TextDecoration? = null,
    textAlign: TextAlign? = null,
    lineHeight: TextUnit = TextUnit.Inherit,
    overflow: TextOverflow = TextOverflow.Clip,
    softWrap: Boolean = true,
    maxLines: Int = Int.MAX_VALUE,
    onTextLayout: (TextLayoutResult) -> Unit = {},
    style: TextStyle = currentTextStyle()
)
```

* **text** – the text to be displayed
  * required
* **modifier** – the modifier to be applied to the composable
* **color** – the Color to be used for the text
* **fontSize** – the font size to be applued
* **fontStyle** – the font style to be applied
* **fontFamily** – the font family to be applied
* **letterSpacing** – the spacing to be applied between letters
* **textDecoration** – the decoration to be applied to the text
* **textAlign** – the alignment to be applied to the text
* **lineHeight** – the line height to be applied
* **overflow** – the method used for handling text overflow
* **softWrap** – whether or not text should be soft wrapped
* **maxLines** – the maximum number of lines allowed for text
* **onTextLayout** – callback to be triggered when text layout has completed
* **style** – the style to be applied to the text

### Displaying text
  
```kotlin
Text(
    text = "Simple text"
)
```

### Colored text
  
```kotlin
Text(
    text = "Colored text",
    color = Color.Red
)
```

### Sized font
  
```kotlin
Text(
    text = "Colored text",
    fontSize = 16.sp
)
```

### Applied font family
  
```kotlin
Text(
    text = "Colored text",
    fontFamily = FontFamily.Monospace
)
```

### Style font
  
```kotlin
Text(
    text = "Colored text",
    fontStyle = FontStyle.Italic
)
```

### Weighted text
  
```kotlin
Text(
    text = "Colored text",
    fontStyle = FontStyle.Italic
)
```

### Maximum line count
  
```kotlin
Text(
    text = "Max line length of 1 text that is using the default property for text overflow",
    maxLines = 1
)
```

### Ellipsis line
  
```kotlin
Text(
    text = "Max line length of 1 text that declares the use of Ellipsis for text overflow",
    maxLines = 1,
    overflow = TextOverflow.Ellipsis
)
```

### Clipped line
  
```kotlin
Text(
    text = "Max line length of 1 text that declares the use of Clip for text overflow",
    maxLines = 1,
    overflow = TextOverflow.Clip
)
```

### Styled text
  
```kotlin
Text(
    text = "Large font size",
    style = TextStyle(fontSize = 28.sp)
)
```

### Aligned text
  
```kotlin
Text(
    text = "Max line length of 1 text that declares the use of Clip for text overflow",
    textAlign = TextAlign.Center
)
```