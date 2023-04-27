# simpleful.css

<a href="https://github.com/ergevozko/simpleful.css">
  <img align="right" alt="simpleful.css" height="64" src="assets/logo.svg" width="64">
</a>

Very simple but useful CSS modules to make your simple website good looking and responsive.

![GitHub release (latest SemVer)](https://img.shields.io/github/v/release/ergevozko/simpleful.css?style=flat-square)

## Features
- Resething _(reset thing)_ CSS to fix cross-browser inconsistencies and bugs.
- Responsive grid container based on the [flex](https://developer.mozilla.org/en-US/docs/Web/CSS/CSS_Flexible_Box_Layout) display property.
- Simple and minimalist styling for most commonly used HTML elements.
- Built with a mobile-first approach to achieve responsive layout.
- Easy to use and customized.
- Lightweight file size.

## How to use
Choose 2 methods below and put the stylesheet `<link>` into your `<head>`:

### Full Build
Simply copy GitHub CDN below…

```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/ergevozko/simpleful.css@0.1.0/dist/simpleful.min.css">
```

### Custom Build
There's also a modular version in [`src`](https://github.com/ergevozko/simpleful.css/tree/main/src) directory
where you can choose the components you need inside `src/optional` folder.
But you must compile them manually with `src/variables.css` and `src/core/base.css` into single stylesheet or follow the order below…

- `src/variables.css`: A CSS Custom Properties (CSS Variable) that allows you to [change theme color](#theming) by just changing the values of the variables.
- `src/core/base.css`: The core of simpleful.css that include our Resething CSS. Without our styling may not be working as expected.
- `src/optional/richtext.css`: Very simple css for all text level semantics element.
- `src/optional/button.css`: Very simple css for button element.
- `src/optional/form.css`: Very simple css for any forms element.
- `src/optional/table.css`: Very simple css for table element.
- `src/optional/flexgrid.css`: Responsive grid container based on the flex display property or flexbox.

> **Note**: Be aware that in two methods above we use CSS Custom Properties and some legacy browsers like Internet Explorer 11 (or older version) doesn't support it.
If you want to override simpleful.css theme but still compatible with IE, you need to read [this](#how-to-support-internet-explorer).

## Need to know
More information you must know and remember…

### Template requirements
Be sure to have your template set up with `<!doctype html>` for HTML5 doctype and viewport `<meta>` tag for proper responsive behaviors.
```html
<!doctype html>
<html>
  <head>
    <!-- Required meta tags -->
    <meta charset="utf-8">
    <meta name="viewport" content="width=device-width, initial-scale=1">
    
    <!-- Stylesheet -->
    <link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/ergevozko/simpleful.css@0.1.0/dist/simpleful.min.css">
  </head>
  <body>
    …
  </body>
</html>
```

### Theming

> **Note**: If you use a version with support for Internet Explorer,
please skip this and read [How to support Internet Explorer](#how-to-support-internet-explorer) instead!

Build your own theme is super easy to do! With our CSS Custom Properties (variables) to define its base styles such as colors,
you only need to change any variables in `src/variables.css` or add your own stylesheet after simpleful.css to override the default variables.

This example will make `<body>` have white background color…
```html
<link rel="stylesheet" href="https://cdn.jsdelivr.net/gh/ergevozko/simpleful.css@0.1.0/dist/simpleful.min.css" />
<style>
  :root {
    --rg-body-bg: #ffffff;
  }
</style>
```
Here's a list of all the variables you can change to your liking…

<details>

- `--rg-main`: theme main color, also for **Link** color and default **Button** background
- `--rg-body-bg`: background color for **Body** element
- `--rg-body-color`: text color for **Body** element
- `--rg-border`: default **border** color
- `--rg-link-hover`: text color for **Link** on hover
- `--rg-heading`: text color **Heading**
- `--rg-code-color`: text color for **Computer Code** elements
- `--rg-button-color`: text color for default **Button**
- `--rg-button-hover`: background color for default **Button** on hover
- `--rg-input-bg`: background color for **Form Input**
- `--rg-input-color`: text color for **Form Input**
- `--rg-input-placeholder`: text color for **Form Input:Placeholder**
- `--rg-input-disabled-bg`: background color for **Form Input:Disabled**
- `--rg-light`: light text/background color
- `--rg-muted`: muted text/background color
- `--rg-other-bg`: background color for **Computer Code** and **Table Striped** element
- `--rg-font-sans-serif`: theme main font
- `--rg-font-mono`: theme mono font

</details>

### Class prefix
Every name of our class always begin with `rg-` to avoid conflicts with other CSS.
In some cases, we may add some _abbreviations string_ to keep the class names concise for building responsively with [media query breakpoints](#breakpoints).

### Breakpoints
Also called media query breakpoints, it's needed to control how the layout can adapts to specific screen widths. 
Designed to be _mobile-first_ to give proper responsive layout, these are 5 default breakpoints based on our responsive grid container…

Breakpoint | Media Query                       | Dimension    | Class Name  |
-----------|-----------------------------------|--------------|------------ |
_None_     | _None_                            | _All_        | `rg-*`      |
`xs`       | `@media (min-width:320px) { … }`  | ≥ 320px      | `rg:xs-*`   |
`sm`       | `@media (min-width:375px) { … }`  | ≥ 375px      | `rg:sm-*`   |
`md`       | `@media (min-width:768px) { … }`  | ≥ 768px      | `rg:md-*`   |
`lg`       | `@media (min-width:1024px) { … }` | ≥ 1024px     | `rg:lg-*`   |
`xl`       | `@media (min-width:1280px) { … }` | ≥ 1280px     | `rg:xl-*`   |

## Browser support

| Chrome | Edge   | Firefox  | Safari  | Opera  |  IE  |
|--------|--------|----------|---------|--------|------|
| 49+    | 16+    | 31+      | 10+     | 36+    |  ❌ |

### How to support Internet Explorer
If you are targeting browsers without support for CSS Custom Properties and still want to apply your own theming,
you'll need to make your changes in the source files inside `src/core` and `src/optional` folder themselves. This works like the following:
- Open the CSS files using your text/code editor.
- Find any CSS property with value `var(--rg-*)` variables.
- Change the variables to your desired color code.
- Compile all css except `variables.css` files.


## Help us
Please let us know if you find any bugs, have suggestion or question by filing an issue on our [GitHub issues](https://github.com/ergevozko/simpleful.css/issues).
