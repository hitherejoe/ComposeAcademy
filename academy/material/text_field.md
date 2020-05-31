---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Text Field
description: Display a standard text field for textual input
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/textField.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun TextField(
    value: TextFieldValue,
    onValueChange: (TextFieldValue) -> Unit,
    modifier: Modifier = Modifier,
    textColor: Color = Color.Unset,
    textStyle: TextStyle = currentTextStyle(),
    keyboardType: KeyboardType = KeyboardType.Text,
    imeAction: ImeAction = ImeAction.Unspecified,
    onFocusChange: (Boolean) -> Unit = {},
    onImeActionPerformed: (ImeAction) -> Unit = {},
    visualTransformation: VisualTransformation = VisualTransformation.None,
    onTextLayout: (TextLayoutResult) -> Unit = {},
    onTextInputStarted: (SoftwareKeyboardController) -> Unit = {},
    cursorColor: Color = contentColor()
)
```

* **value** – the current state of the text field content
  * required

* **onValueChange** – callback triggered whenever the input content is changed
  * required

* **modifier** – modifier to be applued to the text field

* **textColor** – color to be used for textual content

* **textStyle** – style to be used for textual content

* **keyboardType** – the type of keyboard to be used for text input. (See [KeyboardType]())

* **imeAction** – the ime action to be used for the keyboard

* **onFocusChange** – callback used for when focus changes on the composable

* **onImeActionPerformed** – callback used when the ime action is performed

* **visualTransformation** – transformations to be applied to the textual content

* **onTextLayout** – callback triggered when text layout has been calculated

* **onTextInputStarted** – callback triggered when text input has begun

* **cursorColor** – color to be used for the text field cursor

## Examples

### Text Field Value

The TextFieldValue class is used to represent the state of the TextField. Within the change callback for the composable, this class will be returned to represent the current state.

```kotlin
data class TextFieldValue(
    val text: String = "",
    val selection: TextRange = TextRange(0, 0)
)
```

### Minimal Text Field
  
```kotlin
val state = state { TextFieldValue(text = "Hello") }
TextField(
    value = state.value, onValueChange = {
        state.value = it
    }, textColor = Color.Black,
    modifier = Modifier.padding(16.dp).fillMaxWidth()
)
```

### Styled Text Field
  
```kotlin
val state = state { TextFieldValue(text = "Hello") }
TextField(
    value = state.value, onValueChange = {
        state.value = it
    },
    modifier = Modifier.padding(16.dp).fillMaxWidth(),
    textColor = Color.Red,
    cursorColor = Color.Blue,
    textStyle = TextStyle(fontSize = 20.sp)
)
```

### IME Action Text Field

```kotlin
val state = state { TextFieldValue(text = "Hello") }
TextField(value = state.value, onValueChange = {
    state.value = it
},
    modifier = Modifier.padding(16.dp).fillMaxWidth(),
    imeAction = ImeAction.Next,
    onImeActionPerformed = {

    })
```
