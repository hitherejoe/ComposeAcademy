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

<p align="center">
  <img src="/academy/layout/media/arrange_top.png">
</p>


## Arrange items at the bottom

```kotlin
Arrangement.Bottom
```

<p align="center">
  <img src="/academy/layout/media/arrange_bottom.png">
</p>


## Arrange items at the start

```kotlin
Arrangement.Start
```

<p align="center">
  <img src="/academy/layout/media/arrange_start.png">
</p>


## Arrange items at the end

```kotlin
Arrangement.End
```

<p align="center">
  <img src="/academy/layout/media/arrange_end.png">
</p>


## Arrange items in the center

```kotlin
Arrangement.Center
```

<p align="center">
  <img src="/academy/layout/media/arrange_center_row.png">
</p>

<p align="center">
  <img src="/academy/layout/media/arrange_center_column.png">
</p>


## Arrange items using SpaceEvenly

```kotlin
Arrangement.SpaceEvenly
```
![](/academy/layout/media/arrange_space_evenly_row.png)

![](/academy/layout/media/arrange_space_evenly_column.png)

## Arrange items using SpaceBetween

```kotlin
Arrangement.SpaceBetween
```

![](/academy/layout/media/arrange_space_between_row.png)

![](/academy/layout/media/arrange_space_between_column.png)

## Arrange items using SpaceAround

```kotlin
Arrangement.SpaceAround
```

![](/academy/layout/media/arrange_space_around_row.png)

![](/academy/layout/media/arrange_space_around_column.png)
