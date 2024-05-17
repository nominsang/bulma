---
title: Bulma 的 CSS 变量
layout: docs
markdown: true
theme: features
doc-tab: 特色
doc-subtab: css-变量
breadcrumb:
  - home
  - documentation
  - features
  - features-css-variables
---

所有 Bulma 组件由 **CSS 变量**（也叫做 CSS 定制属性）美化。[更多相关信息参阅 MDN 参考](https://developer.mozilla.org/en-US/docs/Web/CSS/Using_CSS_custom_properties)。

例如：`.title` 元素是如何美化的：

```css
.title {
  color: var(--bulma-title-color);
  font-size: var(--bulma-title-size);
  font-weight: var(--bulma-title-weight);
  line-height: var(--bulma-title-line-height);
}
```

## 作用域

Bulma CSS 变量定义：

- 在**全局（global）**范围 `:root`
- 在**组件（component）**范围，如 `.button`

CSS 变量在特定域范围（如 `.button`）的值会覆盖其在全局范围域的值。

```css
:root {
  /* Default global value */
  --bulma-size-medium: 1.25rem;
}

.button {
  /* Overrides the global value */
  --bulma-size-medium: 1.5rem;
}
```

## 前缀（Prefix）

所有 Bulma CSS 变量都有前缀 `bulma-`（包括短横）。当您查看网页的时候会看到：

<img src="/assets/images/content-inspect.png" alt="Inspect CSS variables" width="640" height="340">

该前缀可以通过设置 Sass 变量 `$cssvars-prefix` 修改：

```scss
@use "bulma/sass" with (
  $cssvars-prefix: "my-prefix-"
);
```

## 主题（Theme）

全局 CSS 变量定义在 `:root` 级别，这就定义了 **Bulma 主题**。一款主题其实就是一组 CSS 变量的集合。

<p>
  <a href="{{ site.url }}/documentation/features/themes/">
    阅读更多关于主题信息
  </a>
</p>
