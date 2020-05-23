---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Strings
description: Used to access colors from an applications resources

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
