---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Filled Text Field
description: Display a text field for textual input with a filled background
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/filledTextField.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

### Text Field Value State

```kotlin
@Composable
fun FilledTextField(
    value: TextFieldValue,
    onValueChange: (TextFieldValue) -> Unit,
    label: @Composable () -> Unit,
    modifier: Modifier = Modifier,
    textStyle: TextStyle = currentTextStyle(),
    placeholder: @Composable (() -> Unit)? = null,
    leadingIcon: @Composable (() -> Unit)? = null,
    trailingIcon: @Composable (() -> Unit)? = null,
    isErrorValue: Boolean = false,
    visualTransformation: VisualTransformation = VisualTransformation.None,
    keyboardType: KeyboardType = KeyboardType.Text,
    imeAction: ImeAction = ImeAction.Unspecified,
    onImeActionPerformed: (ImeAction, SoftwareKeyboardController?) -> Unit = { _, _ -> },
    onFocusChange: (Boolean) -> Unit = {},
    onTextInputStarted: (SoftwareKeyboardController) -> Unit = {},
    activeColor: Color = MaterialTheme.colors.primary,
    inactiveColor: Color = MaterialTheme.colors.onSurface,
    errorColor: Color = MaterialTheme.colors.error,
    backgroundColor: Color = MaterialTheme.colors.onSurface,
    shape: Shape =
        MaterialTheme.shapes.small.copy(bottomLeft = ZeroCornerSize, bottomRight = ZeroCornerSize)
)
```

* **value** – the current state of the text field content
  * required

* **onValueChange** – callback triggered whenever the input content is changed
  * required

* **label** – label to be displayed for the text field
  * required

* **modifier** – modifier to be applued to the text field

* **textStyle** – style to be used for textual content

* **placeholder** – placeholder to be displayed when no text has been input

* **leadingIcon** – icon to be displayed at the start of the composable

* **trailingIcon** – icon to be displayed at the end of the composable

* **isErrorValue** – is the composable current in an error state

* **visualTransformation** – transformations to be applied to the textual content

* **keyboardType** – the type of keyboard to be used for text input. (See [KeyboardType]())

* **imeAction** – the ime action to be used for the keyboard

* **onImeActionPerformed** – callback used when the ime action is performed

* **onFocusChange** – callback used for when focus changes on the composable

* **onTextInputStarted** – callback triggered when text input has begun

* **activeColor** – color to be used for content when the composable is active

* **inactiveColor** – color to be used for content when the composable is inactive

* **errorColor** – color to be used for content when the composable is in an error state

* **backgroundColor** – color to be used for background of the composable

* **shape** – shape to be used for the filled area of the composable

### String State

```kotlin
@Composable
fun FilledTextField(
    value: String,
    onValueChange: (String) -> Unit,
    label: @Composable () -> Unit,
    modifier: Modifier = Modifier,
    textStyle: TextStyle = currentTextStyle(),
    placeholder: @Composable (() -> Unit)? = null,
    leadingIcon: @Composable (() -> Unit)? = null,
    trailingIcon: @Composable (() -> Unit)? = null,
    isErrorValue: Boolean = false,
    visualTransformation: VisualTransformation = VisualTransformation.None,
    keyboardType: KeyboardType = KeyboardType.Text,
    imeAction: ImeAction = ImeAction.Unspecified,
    onImeActionPerformed: (ImeAction, SoftwareKeyboardController?) -> Unit = { _, _ -> },
    onFocusChange: (Boolean) -> Unit = {},
    onTextInputStarted: (SoftwareKeyboardController) -> Unit = {},
    activeColor: Color = MaterialTheme.colors.primary,
    inactiveColor: Color = MaterialTheme.colors.onSurface,
    errorColor: Color = MaterialTheme.colors.error,
    backgroundColor: Color = MaterialTheme.colors.onSurface,
    shape: Shape =
        MaterialTheme.shapes.small.copy(bottomLeft = ZeroCornerSize, bottomRight = ZeroCornerSize)
)
```

* **value** – the current value entered into the text field
  * required

* **onValueChange** – callback triggered whenever the input content is changed
  * required

* **label** – label to be displayed for the text field
  * required

* **modifier** – modifier to be applued to the text field

* **textStyle** – style to be used for textual content

* **placeholder** – placeholder to be displayed when no text has been input

* **leadingIcon** – icon to be displayed at the start of the composable

* **trailingIcon** – icon to be displayed at the end of the composable

* **isErrorValue** – is the composable current in an error state

* **visualTransformation** – transformations to be applied to the textual content

* **keyboardType** – the type of keyboard to be used for text input. (See [KeyboardType]())

* **imeAction** – the ime action to be used for the keyboard

* **onImeActionPerformed** – callback used when the ime action is performed

* **onFocusChange** – callback used for when focus changes on the composable

* **onTextInputStarted** – callback triggered when text input has begun

* **activeColor** – color to be used for content when the composable is active

* **inactiveColor** – color to be used for content when the composable is inactive

* **errorColor** – color to be used for content when the composable is in an error state

* **backgroundColor** – color to be used for background of the composable

* **shape** – shape to be used for the filled area of the composable

## Examples

### Text Field Value

The TextFieldValue class is used to represent the state of the TextField. Within the change callback for the composable, this class will be returned to represent the current state.

```kotlin
data class TextFieldValue(
    val text: String = "",
    val selection: TextRange = TextRange(0, 0)
)
```

### Minimal Filled Text Field
  
```kotlin
val state = state { TextFieldValue(text = "Hello") }
FilledTextField(value = state.value, onValueChange = {
    state.value = it
}, label = {
    Text(text = "This is a label")
})
```

### Filled Text Field with placeholder
  
```kotlin
val state = state { TextFieldValue(text = "Hello") }
FilledTextField(value = state.value, onValueChange = {
    state.value = it
}, label = {
    Text(text = "This is a label")
}, placeholder = {
    Text(text = "This is a placeholder")
})
```

### Filled Text Field with Icons

```kotlin
val state = state { TextFieldValue(text = "Hello") }
FilledTextField(value = state.value, onValueChange = {
    state.value = it
}, label = {
    Text(text = "This is a label")
}, leadingIcon = {
    Icon(Icons.Filled.Info)
}, trailingIcon = {
    Icon(Icons.Filled.Check)
})
```

### Colored Filled Text Field

```kotlin
val state = state { TextFieldValue(text = "Hello") }
FilledTextField(value = state.value, onValueChange = {
    state.value = it
}, label = {
    Text(text = "This is a label")
}, 
activeColor = Color.Black,
inactiveColor = Color.Gray,
errorColor = Color.Red)
```
