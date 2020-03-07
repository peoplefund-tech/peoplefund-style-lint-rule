# Peoplefund Style Lint Rule

[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)

Stylelint config that sorts related property declarations by grouping together following the order:

1.  Positioning
2.  Box Model
3.  Typography
4.  Visual
5.  Animation
6.  Misc

```css
.declaration-order {
  /* Positioning */
  position: absolute;
  top: 0;
  right: 0;
  bottom: 0;
  left: 0;
  z-index: 10;

  /* Box Model */
  display: block;
  float: right;
  width: 100px;
  height: 100px;
  margin: 10px;
  padding: 10px;

  /* Typography */
  color: #888;
  font: normal 16px Helvetica, sans-serif;
  line-height: 1.3;
  text-align: center;

  /* Visual */
  background-color: #eee;
  border: 1px solid #888;
  border-radius: 4px;
  opacity: 1;

  /* Animation */
  transition: all 1s;

  /* Misc */
  user-select: none;
}
```

## Usage

1.  Add `stylelint`, `stylelint-order` and this package to your project:

```bash
npm install --save-dev stylelint stylelint-order stylelint-config-rational-order
# or, if you prefer yarn over npm:
yarn add --dev stylelint stylelint-order stylelint-config-rational-order
```

2.  Add this package to the end of your extends array inside Stylelint
    configuration (.stylelintrc for example):

```javascript
{
  "extends": [
    // "stylelint-config-standard",
    "stylelint-config-rational-order"
  ]
}
```

This shareable config contains the following:
```javascript
{
  "plugins": [
    "stylelint-order",
    "stylelint-config-rational-order/plugin"
  ],
  "rules": {
    "order/properties-order": [],
    "plugin/peoplefund-order": [true, {
      "border-in-box-model": false,
      "empty-line-between-groups": false,
    }]
  }
}
```

Since it adds `stylelint-order` and `stylelint-config-rational-order` to plugins and also adds required rules, you don't have to do this yourself when extending this config.


## Optional options / rules

#### border-in-box-model

Defines to which group the **border** property belongs to.

If `true` **border** property belongs to the **box model section**.
The default value is `false` (**border** property belongs to the **visual section**).


#### empty-line-between-groups

If `true` adds an empty line between groups. The default value is `false`.
