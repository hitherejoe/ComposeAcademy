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

## Accessing an integer resource

Using the **integerResource** function, a single integer resource can be accessed.

```kotlin
<integer name="some_integer">5</integer>

repeat(integerResource(id = R.integer.some_integer)) {
    Text(text = it.toString())
}
```

## Accessing an integer array resource

Using the **integerArrayResource** function, an array of strings can be accessed.

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

Using the **booleanResource** function, a single integer resource can be accessed.

```kotlin
<bool name="is_feature_enabled">true</bool>

Text(text = "Is enabled: ${booleanResource(id = R.bool.is_feature_enabled)}",
    modifier = Modifier.padding(16.dp))
```

## Accessing a dimension resource

Using the **dimensionResource** function, a single dimension resource can be accessed.

```kotlin
<dimen name="padding">16dp</dimen>

Text(text = "Adding some padding",
    modifier = Modifier.padding(dimensionResource(id = R.dimen.padding)))
```