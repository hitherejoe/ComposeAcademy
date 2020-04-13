---
# Page settings
layout: default
keywords:
comments: false
description: The checbox is used to

# Micro navigation
micro_nav: true

---

# Constructor

```kotlin
@Composable
fun Checkbox(
    checked: Boolean,
    onCheckedChange: ((Boolean) -> Unit)?,
    modifier: Modifier = Modifier.None,
    color: Color = (+MaterialTheme.colors()).secondary
)
```

# Simple checkbox

```kotlin
Checkbox(
    checked = false,
    onCheckedChange = { }
)
```

# Handling check changes


# Styled checkbox

```kotlin
Checkbox(
    checked = false,
    onCheckedChange = { },
    color = Color.Red
)
```


# Enabling / Disabling the checkbox

```kotlin
@Composable
fun CheckboxComponent(formState: FormState) {
    Checkbox(
        checked = formState.optionChecked,
        onCheckedChange = { },
        enabled = formState.enabled
    )
}
```

# Checkbox with label
