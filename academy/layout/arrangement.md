---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Arrangement
description: Declare how the children should be laid out within their parent containers
buttons:
  - icon: github
    content: View in Playground
    url: "https://github.com/hitherejoe/ComposeAcademy-Playground/blob/master/app/src/main/java/co/joebirch/composeplayground/layout"
    external_url: true

# Micro navigation
micro_nav: false

---

## Interface

There are three interfaces which are used to define the available Arrangment values.

```kotlin
// provides arrangement values available for all layout orientations
interface Arrangement

// provides Vertical specific arrangement values
interface Vertical : Arrangement

// provides Horizontal specific arrangement values
interface Horizontal : Arrangement
```

## Arrange items at the top

```kotlin
Arrangement.Top
```

![Arrange bottom](/academy/layout/media/arrange_top.png)

## Arrange items at the bottom

```kotlin
Arrangement.Bottom
```

![Arrange bottom](/academy/layout/media/arrange_bottom.png)

## Arrange items at the start

```kotlin
Arrangement.Start
```

![Arrange end](/academy/layout/media/arrange_start.png)

## Arrange items at the end

```kotlin
Arrangement.End
```

![Arrange end](/academy/layout/media/arrange_end.png)

## Arrange items in the center

```kotlin
Arrangement.Center
```

![Arrange center, row](/academy/layout/media/arrange_center_row.png)

![Arrange center, column](/academy/layout/media/arrange_center_column.png)

## Arrange items using SpaceEvenly

```kotlin
Arrangement.SpaceEvenly
```

![Arrange space evenly, row](/academy/layout/media/arrange_space_evenly_row.png)

![Arrange space evenly, column](/academy/layout/media/arrange_space_evenly_column.png)

## Arrange items using SpaceBetween

```kotlin
Arrangement.SpaceBetween
```

![Arrange space between, row](/academy/layout/media/arrange_space_between_row.png)

![Arrange space between, column](/academy/layout/media/arrange_space_between_column.png)

## Arrange items using SpaceAround

```kotlin
Arrangement.SpaceAround
```

![Arrange space around, row](/academy/layout/media/arrange_space_around_row.png)

![Arrange space around, column](/academy/layout/media/arrange_space_around_column.png)
