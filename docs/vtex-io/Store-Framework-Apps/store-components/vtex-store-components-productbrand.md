---
title: "Product Brand"
slug: "vtex-store-components-productbrand"
excerpt: "vtex.store-components@3.163.4"
hidden: false
createdAt: "2020-06-03T16:04:30.393Z"
updatedAt: "2022-11-22T18:39:23.077Z"
---
The `product-brand` block displays either the **name** or the **logo** of a product's brand.

![product-brand](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-store-components-productbrand-0.png)

## Before you start
Ensure that you have registered [brands](https://help.vtex.com/en/tutorial/what-is-a-brand--QU07yhHoaWcEYseEucOQW) in your store. To do so, follow the [How to register brands](https://help.vtex.com/en/tutorial/registering-brands--tutorials_1414) documentation.

## Configuration

1. Import the `vtex.store-components` app to your theme's dependencies in the `manifest.json` file as in the following example:

```json
  "dependencies": {
    "vtex.store-components": "2.x"
  }
```

2. Add the `product-brand` block to any child of the `store.product` template (Product Details Page template). For example:

```diff
  "store.product": {
    "children": [
      "flex-layout.row#product",
    ]
  },
  "flex-layout.row#product": {
    "children": [
+     "product-brand"
    ]
  },  
```

3. Then, declare the `product-brand` block using the props stated in the [Props](#props) table. For example:

```json
"product-brand": {
    "props": {
      "displayMode": "text"
    }
  },
```

### Configuration

| Prop name | Type | Description | Default value 
| --- | --- | --- | --- |
| `brandId` | `number` | The brand ID.  If no value is declared, the product context should provide the data. | `undefined` |
| `brandName` | `string` | The brand name. If no value is declared, the product context should provide the data. | `undefined` |
| `classes` | `CustomCSSClasses` | Overrides default CSS handles. To better understand how this prop works, check [this document](https://github.com/vtex-apps/css-handles#usecustomclasses). Note that this is only helpful if you're using this block as a React component.| `undefined` |
| `displayMode` | `string` | Defines if the product brand will be displayed by name or logo. Possible values are `logo` and `text`.  | `logo` |
| `excludeBrands` | `array` | The brand names or brand IDs listed in the array will never be displayed by the Brand component. It is usually useful to hide default or test brand names/logos on the store front. | `undefined` |
| `fallbackToText` | `boolean` | Defines the behavior of the Product Brand block when set to display a brand logo but no image is registered in the VTEX admin's Catalog. If `true`, it allows the logo to be replaced with the brand name. If `false`, neither the brand name nor the brand logo are displayed. **This prop is only available for the `logo` display mode.** | `true` |
| `height` | `number` | The logo height. **This prop is only available for the `logo` display mode.** | `100` |
| `loadingPlaceholder` | `string` | Defines if the loading placeholder should have the size of the logo or the text. Possible values are: `logo` and `text`. | `undefined` |
| `logoWithLink` | `boolean` | ![https://img.shields.io/badge/-Deprecated-red](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-store-components-productbrand-1.png) Use `withLink` instead | `false` |
| `withLink` | `enum` | Defines the scenarios in which the product brand should have a link that leads to its website. Possible values are: `none` (never includes the link), `logo` (includes the link whenever the brand logo is displayed), `text` (includes the link whenever the brand name is displayed), and `logoAndText` (includes the link whenever the brand logo or the brand name is displayed).  | `none` |

## Customization 

To apply CSS customizations in this and other blocks, follow the [Using CSS handles for store customization](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-using-css-handles-for-store-customization) guide.

| CSS Handles |
| --- |
| `productBrandContainer` |
| `productBrandName` |
| `productBrandLogo` |
| `productBrandLogoWrapper` |
| `productBrandLogoLink` |
| `productBrandNameLink` |
| `productBrandLogoSpacer` |
| `productBrandNameSpacer` |