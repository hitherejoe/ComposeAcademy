---
# Page settings
layout: default
keywords:
comments: false

# Micro navigation
micro_nav: true

---

# Checkbox

```
@Composable
fun Checkbox(
    checked: Boolean,
    onCheckedChange: ((Boolean) -> Unit)?,
    modifier: Modifier = Modifier.None,
    color: Color = (+MaterialTheme.colors()).secondary
)
```
