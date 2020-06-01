---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Finders
description: Retrieve a reference to components

# Micro navigation
micro_nav: false

---

## Find by tag

```kotlin
findByTag("MyTag")
```

## Find by text

```kotlin
findByText("Hello")
```

## Find all by text

```kotlin
findAllByText("Hello")

findAllByText("Hello").first()
```

## Find all by tag

```kotlin
findAllByTag("MyTag")

findAllByTag("MyTag").first()
```