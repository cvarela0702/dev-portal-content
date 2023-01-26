---
title: "Back To Top Button"
slug: "vtex-store-components-backtotopbutton"
excerpt: "vtex.store-components@3.163.4"
hidden: false
createdAt: "2020-06-03T16:04:30.348Z"
updatedAt: "2022-11-22T18:39:23.174Z"
---
The `back-to-top-button` component is a button that redirects users to the top of the page when clicked.

![Back To Top Button rendered as a text button](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-store-components-backtotopbutton-0.png)

_Back To Top Button rendered as a text button_

![Back To Top Button rendered as a caret icon](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-store-components-backtotopbutton-1.png)

_Back To Top Button rendered as a caret icon_

## Configuration

1. Import the `vtex.store-components` app to your theme's dependencies in the `manifest.json` file as in the following example:

```json
 "dependencies": {
    "vtex.store-components": "3.x"
  }
```

2. Add the `back-to-top-button` block into a store template of your choice. In the example, it will be added to the home page:

```diff
  "store.home": {
    "blocks": [
+     "back-to-top-button",
    ]
  },
```

3. Then, declare the `back-to-top-button` block using the props stated in the [Props](#props) table. For example:

```diff
  "store.home": {
    "blocks": [
     "back-to-top-button",
    ]
  },
+  "back-to-top-button":{
+    "props":{
+      "displayThreshold": 800,
+    }
+  }
```

### Props

| Prop name          | Type     | Description                                                                                                                                                 | Default Value |
| ------------------ | -------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| `display`          | `enum`   | Defines the component rendering. Possible values are: `button` to display a button with a `Back To Top` label text or `caret-icon` to display just an icon. | `button`      |
| `displayThreshold` | `number` | Defines the window Y pixel in which the button will be displayed.                                                                                           | `600`         |

## Customization

To apply CSS customizations in this and other blocks, follow the [Using CSS handles for store customization](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-using-css-handles-for-store-customization) guide.

| CSS Handles                |
| -------------------------- |
| `backToTopButtonActive`    |
| `backToTopButtonContainer` |
| `backToTopButtonHidden`    |