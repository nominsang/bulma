---
title: Bulma 的主题
layout: docs
markdown: true
theme: features
doc-tab: 特色
doc-subtab: 主题
breadcrumb:
  - home
  - documentation
  - features
  - features-themes
---


在 Bulma 中，一个**主题**就是一**组** CSS 变量。

Bulma 自带 2 个主题：

- `light.scss`（必备）
- `dark.scss`（可选）

## 默认主题

由于 Bulma 的所有 CSS 变量都有默认值，所以就有了基于 `/sass/themes/light.scss` 文件的**默认亮色主题**。

还有一个基于 `/sass/themes/dark.scss` 的**暗色主题**。

文件 `/sass/themes/_index.scss` 包含两个主题，每个都有两种方式：

* 基于媒体查询的 `@media (prefers-color-scheme: $name)` 方式
* 基于 HTML 属性 `[data-theme=$name]` 和 CSS 类 `.theme-$name` 选择器的方式

唯一的不同点就是亮色模式已经在顶级属性中定义：`:root`（等同于 `html` 元素——网页中所有 HTML 元素的根元素）。这将确保为所有 CSS 变量设置了**默认**值。

主题的 CSS 设置大致如下：

```css
:root {
    /* CSS Variables */
}

@media (prefers-color-scheme: light) {
  :root {
    /* CSS Variables */
  }
}

@media (prefers-color-scheme: dark) {
  :root {
    /* CSS Variables */
  }
}

[data-theme=light],
.theme-light {
  /* CSS Variables */
}

[data-theme=dark],
.theme-dark {
  /* CSS Variables */
}
```

## 创建一个定制主题

创建主题必须**设置您自己的 CSS 变量**。定制主题需要：

* 主题名，如 `sunrise`
* 主题域，如 `:root`, `[data-theme=sunrise]`, `.theme-sunrise` 或其它三种
* 一组 CSS 变量以及值

### 在浏览器中定制

如果您设置您的 CSS 变量是 `:root` 范围的，您可以**复写** Bulma 默认主题。这可以通过 Sass 或 CSS 定制。

测试 CSS 方法，可以通过下面步骤：

{% include docs/elements/step.html image="images/themes/step-1-inspect.png" content="打开浏览器的检查功能" width=496 height=748 %}
{% include docs/elements/step.html image="images/themes/step-2-html.png" content="选择 `html` 元素" width=528 height=232 %}
{% include docs/elements/step.html image="images/themes/step-3-var.png" content="插入一个新 `--bulma-link-h` 变量值（链接颜色的 hue 值）" width=376 height=120 %}
{% include docs/elements/step.html image="images/themes/step-4-menu.png" content="注意侧栏菜单 CSS Helpers 部分的颜色变化" width=480 height=256 %}
