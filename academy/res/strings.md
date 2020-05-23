---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Strings
description: Used to access strings from an applications resources

# Micro navigation
micro_nav: false

---

## String resources

When it comes to accessing string resources, Jetpack Compose offers the following functionalities.

## Accessing a string resource

Using the **stringResource** function, a single string resource can be accessed.

```kotlin
<string name="app_name">Compose Playground</string>

Text(text = stringResource(id = R.string.app_name))
```

## Formatting a string resource

Using the  **stringResource** function, the formatArgs property can be used to supply an array of strings which are be used to format the initial string.

```kotlin
<string name="app_name_formatting">This is %s</string>

Text(text = stringResource(id = R.string.app_name_formatting,
        formatArgs = *arrayOf(stringResource(id = R.string.app_name))))
```

## Accessing a string array resource

Using the **stringArrayResource** function, an array of strings can be accessed.

```kotlin
<string-array name="sample_array">
    <item>One</item>
    <item>Two</item>
    <item>Three</item>
</string-array>

stringArrayResource(id = R.array.sample_array).forEach {
    Text(text = it,
        modifier = Modifier.padding(16.dp))
}
```
