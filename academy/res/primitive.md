---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Strings
description: Used to access primitive values from application resources. Currently supports integers, booleans and dimension values

# Micro navigation
micro_nav: false

---

# String resources

When it comes to accessing string resources, Jetpack Compose offers the following functionalities.

## Accessing an integer resource

```kotlin
<integer name="some_integer">5</integer>

repeat(integerResource(id = R.integer.some_integer)) {
    Text(text = it.toString())
}
```

## Accessing an integer array resource

```kotlin
<integer-array name="some_integer_array">
    <item>0</item>
    <item>1</item>
    <item>2</item>
    <item>3</item>
</integer-array>

integerArrayResource(id = R.array.some_integer_array).forEach {
    Text(text = it.toString(),
        modifier = Modifier.padding(16.dp))
}
```

## Accessing a boolean resource

```kotlin
<bool name="is_feature_enabled">true</bool>

Text(text = "Is enabled: ${booleanResource(id = R.bool.is_feature_enabled)}",
    modifier = Modifier.padding(16.dp))
```

## Accessing a dimension resource

```kotlin
<dimen name="padding">16dp</dimen>

Text(text = "Is enabled: ${booleanResource(id = R.bool.is_feature_enabled)}",
    modifier = Modifier.padding(16.dp))

Text(text = "Adding some padding",
    modifier = Modifier.padding(dimensionResource(id = R.dimen.padding)))
```