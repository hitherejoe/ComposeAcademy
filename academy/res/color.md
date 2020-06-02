---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Strings
description: Used to access colors from an applications resources
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/resource/colorResource.kt"
    external_url: true

# Micro navigation
micro_nav: false

---

## Accessing a color resource

Using the **colorResource** function, a single color resource can be accessed.

```kotlin
<color name="colorPrimary">#6200EE</color>

Text(text = stringResource(id = R.string.app_name),
    color = colorResource(id = R.color.colorPrimary))
```
