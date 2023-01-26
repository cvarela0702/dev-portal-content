---
title: "Add To Cart Button"
slug: "vtex-add-to-cart-button"
excerpt: "The add-to-cart button is responsible for adding products in the Minicart."
hidden: false
createdAt: "2020-06-03T15:19:30.080Z"
updatedAt: "2022-04-11T12:41:12.534Z"
---

The `add-to-cart-button` block is responsible for adding products in the [Minicart](https://vtex.io/docs/components/all/vtex.minicart/) (`minicart.v2`).

![image](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtex-add-to-cart-button-0.png)

> ⚠️ **The Add To Cart Button only works in stores using the Minicart v2**. In this scenario, it successfully works in the Shelf component as well as in the Product Details page. **If you are using the [Minicart v1](https://github.com/vtex-apps/minicart/blob/383d7bbd3295f06d1b5854a0add561a872e1515c/docs/README.md), configure the [Buy Button block](https://vtex.io/docs/components/all/vtex.store-components/buybutton/) in the Product Details page and the [Product Summary Buy Button](https://vtex.io/docs/components/all/vtex.product-summary/product-summary-buy-button/) in the Shelf component instead**.

## Configuration

1. Import the `vtex.add-to-cart-button` app to your theme's dependencies in the manifest.json, for example:

```json
"dependencies": {
  "vtex.add-to-cart-button": "0.x"
}
```

2. Add the `add-to-cart-button` to other theme block using the product context, such as the `product-summary.shelf`. In the example below, the `add-to-cart-button` is added to the `flex-layout.row` block from the `store.product` template (which uses the product context):

```json
  "store.product": {
    "children": [
      "flex-layout.row#product",
    ]
  },
  "flex-layout.row#product": {
    "children": [
      "add-to-cart-button"
    ]
  }
```

| Prop name               | Type      | Description                                                                       | Default value        |
| ----------------------- | --------- | --------------------------------------------------------------------------------- | -------------------- |
| `onClickBehavior`       | `enum` | Controls what happens when users click on the button. Possible values are: `go-to-product-page`, `add-to-cart`, and `ensure-sku-selection` (if multiple SKUs are available, users will be redirected to the product page to select the desired one. If the product only has 1 SKU available, it will be added to the cart once the button is clicked on). | `add-to-cart`              |
| `onClickEventPropagation` | `enum` | Controls whether the 'onClick' event (triggered upon user clicks) should be spread to the page's parent elements. Possible values are: `disabled` and `enabled`. | `disabled` |
| `isOneClickBuy`         | `boolean` | Whether the user should be redirected to the checkout page (`true`) or not (`false`) when the Add To Cart Button is clicked on.  | `false`              |
| `customOneClickBuyLink` | `string`  | Defines the link to where users will be redirected when the Add To Cart Button is clicked on and the `isOneClickBuy` prop is set to `true`. | `/checkout/#/cart` |
| `customToastUrl`        | `string`  | Defines the link to where users will be redirected when the Toast (pop-up notification displayed when adding an item to the minicart) is clicked on.  | `/checkout/#/cart`   |
| `text` | `string` | Defines a custom text message to be displayed on the Add To Cart Button. | `Add to cart` *(automatic translation will be applied according to your store's default language)* |
| `unavailableText` | `string` | Defines a custom text message to be displayed on the Add To Cart Button when a product is unavailable. | `Unavailable` *(automatic translation will be applied according to your store's default language)* |
| `customPixelEventId` | `string` | Define the `id` for the event that will be sent by the the button upon user interaction. | `undefined`   |

## Customization

In order to apply CSS customizations in this and other blocks, follow the instructions given in the recipe on [Using CSS Handles for store customization](https://vtex.io/docs/recipes/style/using-css-handles-for-store-customization).

| CSS Handles           |
| --------------------- |
| `buttonText`          |
| `buttonDataContainer` |
| `tooltipLabelText`    |
