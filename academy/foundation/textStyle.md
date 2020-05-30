---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Text Style
description: Apply styling to text composables
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/foundation/textStyle.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

```kotlin
@Immutable
data class TextStyle(
    val color: Color = Color.Unset,
    val fontSize: TextUnit = TextUnit.Inherit,
    val fontWeight: FontWeight? = null,
    val fontStyle: FontStyle? = null,
    val fontSynthesis: FontSynthesis? = null,
    val fontFamily: FontFamily? = null,
    val fontFeatureSettings: String? = null,
    val letterSpacing: TextUnit = TextUnit.Inherit,
    val baselineShift: BaselineShift? = null,
    val textGeometricTransform: TextGeometricTransform? = null,
    val localeList: LocaleList? = null,
    val background: Color = Color.Unset,
    val textDecoration: TextDecoration? = null,
    val shadow: Shadow? = null,
    val textAlign: TextAlign? = null,
    val textDirectionAlgorithm: TextDirectionAlgorithm? = null,
    val lineHeight: TextUnit = TextUnit.Inherit,
    val textIndent: TextIndent? = null
)
```

* **color** – the Color to be used for the text
* **fontSize** – the font size to be applied
* **fontWeight** – the weight to be applied to the font
* **fontStyle** – the font style to be applied
* **fontSynthesis** – declares whether font weight shuold be synthesied when not found for the requested weight in the current font family
* **fontFamily** – the font family to be applied
* **fontFeatureSettings** -
* **letterSpacing** – the spacing to be applied between letters
* **baselineShift** – how much the text is shifted up from the current baseline
* **textGeometricTransform** - geometric transofmration applied to the text
* **localeList** – locale list to select locale specific glyphs from
* **background** – background color to use for the composable
* **textDecoration** – decorations to be painted onto the text
* **shadow** – shadow to be applied to the text
* **textAlign** – the alignment to be applied to the text
* **textDirectionAlgorithm** – the algorithm to resolve the final text and paragraph direction
* **lineHeight** – line height applied to the text paragraph
* **textIndent** - indentation to be applied to the text paragraph

### Using Text Style
  
```kotlin
Text(
    text = "Font size",
    style = TextStyle(fontSize = 28.sp)
)
```

### Colored text style
  
```kotlin
TextStyle(color = Color.Red)
```

### Background Color
  
```kotlin
TextStyle(background = Color.Red)
```

### Shadow
  
```kotlin
TextStyle(shadow = Shadow(Color.Gray))
```

### Text Direction Algorithm
  
```kotlin
TextStyle(textDirectionAlgorithm = TextDirectionAlgorithm.ContentOrRtl)
```
  
```kotlin
ContentOrLtr,
ContentOrRtl,
ForceLtr,
ForceRtl
```

### Decoration
  
```kotlin
TextStyle(textDecoration = TextDecoration.LineThrough)
```

```kotlin
None
Underline
LineThrough
```

```kotlin
TextStyle(textDecoration = TextDecoration.combine(listOf(
    TextDecoration.LineThrough, TextDecoration.Underline
)))
```

### Font Weight
  
```kotlin
Text(
    text = "Font weight",
    style = TextStyle(fontWeight = FontWeight.Bold),
    modifier = Modifier.padding(16.dp)
)
```

```kotlin
val W100 = FontWeight(100)
val W200 = FontWeight(200)
val W300 = FontWeight(300)
val W400 = FontWeight(400)
val W500 = FontWeight(500)
val W600 = FontWeight(600)
val W700 = FontWeight(700)
val W800 = FontWeight(800)
val W900 = FontWeight(900)

val Thin = W100
val ExtraLight = W200
val Light = W300
val Normal = W400
val Medium = W500
val SemiBold = W600
val Bold = W700
val ExtraBold = W800
val Black = W900
```

### Font style
  
```kotlin
TextStyle(fontStyle = FontStyle.Italic)
```

```kotlin
Normal
Italic
```

### Letter spacing
  
```kotlin
TextStyle(letterSpacing = 12.sp)
```

### Font synthesis
  
```kotlin
TextStyle(fontSynthesis = FontSynthesis.Weight)
```

```kotlin
None,
Weight,
Style,
All
```

### Baseline shift
  
```kotlin
TextStyle(baselineShift = BaselineShift.Subscript)
```

```kotlin
Superscript
Subscript
None
```

### Line height
  
```kotlin
TextStyle(lineHeight = 16.sp)
```

### Ellipsis line
  
```kotlin
TextStyle(textIndent = TextIndent(firstLine = 16.sp, restLine = 8.sp))
```
