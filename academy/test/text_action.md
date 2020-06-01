---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Text Action
description: Perform text related action on a component

# Micro navigation
micro_nav: false

---

## Enter Text

```kotlin
findByTag("MyTag").doSendText(text = "Some text")
```

## Replace Text

```kotlin
findByTag("MyTag").doReplaceText(text = "Replaced text")
```

## Clear Text

```kotlin
findByTag("MyTag").doClearText()
```

## Perform IME action

```kotlin
findByTag("MyTag").doSendImeAction()
```