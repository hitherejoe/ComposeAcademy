---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Popup
description: Defines a composable used for presenting information to a user via a popup 
buttons:
    - icon: github
      content: View in playground
      url: 'https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/core/popup.kt'
      external_url: true

# Micro navigation
micro_nav: false

---

## Constructors

```kotlin
@Composable
fun Popup(
    alignment: Alignment = Alignment.TopStart,
    offset: IntPxPosition = IntPxPosition(IntPx.Zero, IntPx.Zero),
    popupProperties: PopupProperties = PopupProperties(),
    children: @Composable() () -> Unit
)
```

* **alignment** - the alignment of the popup composable within its container

* **offset** - the offset to be applied to the popup

* **popupProperties** - the additional properties to be applied to the popup

* **children** - the child composables to be displayed within the popup


## Examples 

### Creating a standard popup

At a minimum, a Popup can be created by providing a child component that we  
wish to display as the composable content.

```kotlin
Popup {
    Stack {
        Box(
            Modifier.preferredSize(200.dp, 50.dp),
            shape = RoundedCornerShape(16.dp),
            backgroundColor = Color.Black
        )
        Text(
            text = "Pop up!", modifier = Modifier.gravity(Alignment.Center),
            color = Color.White
        )
    }
}
```

### Popup properties

Above we saw the mention of the PopupProperties class - this allows us to provide  
some additional properties for the popup. Currently the class supports two 
properties via its constructor, with more planned to be added in future.

  * **isFocusable** - whether or not the popup should take the current focus

  * **onDismissRequest** - when the popup is focusable, this is executed when  
  click events are made from outside the popup

```kotlin
@Immutable
data class PopupProperties(
    val isFocusable: Boolean = false,
    val onDismissRequest: (() -> Unit)? = null
)
```

### Creating a dropdown popup

The Dropdown Popup can be used when we wish to offset the popup to be displayed  
in a dropdown format. The Dropdown popup provides several additional properties  
that allow us to acheive this when compared with the standard Popup:

* **dropdownAlignment** - the alignment of the popup composable within its container

* **offset** - the offset to be applied to the popup

* **popupProperties** - the additional properties to be applied to the popup

* **children** - the child composables to be displayed within the popup

```kotlin
DropdownPopup(dropDownAlignment = DropDownAlignment.End) {
    Stack {
        Box(
            Modifier.preferredSize(200.dp, 50.dp),
            shape = RoundedCornerShape(16.dp),
            backgroundColor = Color.Black
        )
        Text(
            text = "Pop up!", modifier = Modifier.gravity(Alignment.Center),
            color = Color.White
        )
    }
}
```