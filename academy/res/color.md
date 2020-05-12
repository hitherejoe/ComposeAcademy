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

# Color resources

When it comes to accessing color resources, Jetpack Compose offers the following functionalities.

## Accessing a color resource

```kotlin
<color name="colorPrimary">#6200EE</color>

Text(text = stringResource(id = R.string.app_name),
    color = colorResource(id = R.color.colorPrimary))
```