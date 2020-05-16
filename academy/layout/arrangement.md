---

# Page settings
layout: default
keywords:
comments: false

# Hero section
title: Arrangement
description: When it comes to the layout of child components inside of their parents, it’s likely we’re going to want to arrange them in some way on both the horizontal and/or vertical axis. The Arrangement interface provides us with the ability to declare how the children of our containers should be laid out

# Micro navigation
micro_nav: false

---

## Interface

```kotlin
interface Arrangement

interface Vertical : Arrangement

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
