---
title: "Elfsight"
slug: "vtex-elfsight"
excerpt: "vtex.elfsight@1.0.0"
hidden: false
createdAt: "2020-07-16T16:18:03.236Z"
updatedAt: "2020-07-16T16:18:03.236Z"
---

Elfsight first party integration app. The [solution](https://elfsight.com/) provides widgets that help website owners to increase sales, engage visitors, collect leads and more.

![image](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-elfsight-0.png)

## Configuration

1. Adding the app as a theme dependency in the `manifest.json` file;

```json
"dependencies": {
  "vtex.elfsight": "1.x"
}
```

2. Add the block `elfsight`, responsible for rendering your Elfsight widget, to your theme `blocks.json` file. Notice: the block can be added to any page template you want.
3. Declare in it the prop `appId` whose value must be the app ID of the widget provided by Elfsight. For example:

```diff
   "footer-layout.desktop": {
     "children": [
+      "elfsight#foobar"
     ]
   },

+  "elfsight#foobar": {
+    "props": {
+      "appId": "4a13d81d-20f3-4661-b472-9de777efe3ed"
+    }
+  }
```

### `elfsight` props

| Prop name    | Type            | Description    | Default value                                                                                                                               |
| ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| `appId`      | `string`       | The app ID of the widget provided by Elfsight. The format should be as follows: `XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX`.      | `undefined`        |

You should get the app ID from the Elfsight admin:

![App Id](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-elfsight-1.png)
