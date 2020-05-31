---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Radio Button
description: Make a selection from a group of available options
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/material/radioButton.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Constructor

There is a single constructor available for creating a new reference  
to a Radio Button component:

```kotlin
@Composable
fun RadioButton(
    selected: Boolean,
    onSelect: (() -> Unit)?,
    color: Color = MaterialTheme.colors.secondary
)
```

* **selected** – whether or not the button is currently selected
  * required
* **onSelect** – a callback that will receive change events for when the  
selected state of the component changes changes
  * required
* **color** – the color to be used for the radio button. If not provided,  
then the secondary color from the application theme will be applied

## Examples

### Simple Radio Button with label

```kotlin
Row {
    RadioButton(
        selected = false,
        onSelect = {  }
    )
    Text(
        text = “hello”
    )
}
```

![Radio button](/academy/material/media/radiobutton.png)

```kotlin
Row {
    RadioButton(
        selected = true,
        onSelect = {  }
    )
    Text(
        text = “hello”
    )
}
```

![Selected radio button](/academy/material/media/selected_radiobutton.png)

### Handling selection changes

Whilst the above looks great, statically defining the checked value, along  
with not reacting to state changed events, doesn’t really resemble how we  
might handle this in a real world scenario. To approach this, let’s being  
by created a new @Model representation that will house the state for our  
Radio Button. Here we’ll use a nullable string to keep a track of the  
selected option:


```kotlin
@Model
class RadioState(var selectedOption: String? = null)
```

Now we have this in place, we can assign values to both our selected and  
onSelect properties. In our composable function we pass a RadioState reference,  
along with a text value which is going to be assigned to our Radio Button. For  
the selected property we’ll simply check whether the given text value matches  
the currently selected option in our RadioState reference. When it comes to the  
onSelect property we will set the selectedOption value within our RadioState  
reference so that the state of the Radio Button is reflected in our model.

```kotlin
@Composable
fun RadioButtonWithLabel(
    text: String,
    formState: RadioState
) {
    Row {
        RadioButton(
            selected = radioState.selectedOption == text,
            onSelect = { 
                radioState.selectedOption = text
            },
            color = Color.Magenta
        )
        Text(
            text = “hello”
        )
    }
}
```

### Styled Radio Button

```kotlin
Row {
    RadioButton(
        selected = true,
        onSelect = {  },
        color = Color.Magenta
    )
    Text(
        text = “hello”
    )
}
```

![Color radio button](/academy/material/media/colored_radiobutton.png)
