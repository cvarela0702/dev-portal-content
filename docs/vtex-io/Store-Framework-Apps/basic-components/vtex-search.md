---
title: "Search"
slug: "vtex-search"
excerpt: "vtex.search@2.14.0"
hidden: false
createdAt: "2020-06-03T15:15:11.555Z"
updatedAt: "2022-10-10T23:25:50.492Z"
---

The VTEX Search app is responsible for handling the new [**VTEX Intelligent Search**](https://help.vtex.com/tracks/vtex-intelligent-search) solution in IO stores by providing new UI components that enhance the search experience, such as the autocomplete feature.

![search-app-gif](https://raw.githubusercontent.com/vtexdocs/dev-portal-content/main/docs/guides/Getting%20Started/search-overview-0_21.gif)

## Configuration

The proper functioning of the Search app components relies on having already installed apps `vtex.admin-search@1.x` and `vtex.search-resolver@1.x` in your store. For more on this, access our [**VTEX Intelligent Search**](https://help.vtex.com/tracks/vtex-intelligent-search) track.

To configure the Search app, check the sections below.

### Add the Search app to your theme's dependencies

Add the `search` app to your theme's dependencies in the `manifest.json` as showed below:

```diff
  "dependencies": {
+   "vtex.search": "2.x"
  }
```

You are now able to use all of the blocks exported by the `search` app. Check the full list below:

| Block name                    | Description             |
| ----------------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| `autocomplete-result-list.v2` | Provides customized autocomplete features in the search bar component, such as top searches, search history, product suggestions or term suggestions. You can read more about the Intelligent Search [autocomplete feature](https://help.vtex.com/en/tracks/vtex-intelligent-search--19wrbB7nEQcmwzDPl1l4Cb/4gXFsEWjF7QF7UtI2GAvhL) on VTEX Help Center. |
| `search-banner`               | Renders a customized banner according to the search query performed.           |
| `did-you-mean`                | Helps users with possible misspelling corrections for the current search query.             |
| `search-suggestions`          | Renders a list of similar search terms for the current search query.          |

> ℹ️ The blocks `search-banner`, `did-you-mean` and `search-suggestions` require you to have [Search Result app](https://developers.vtex.com/vtex-developer-docs/docs/vtex-search-result) version `3.x` or higher installed in your theme.

### Add the Search's blocks into the theme

First, declare the `autocomplete-result-list.v2` block as a child block of the [`search-bar` block](https://developers.vtex.com/vtex-developer-docs/docs/vtex-store-components-searchbar), exported by the Store Components app, for example:

```json
{
  "search-bar": {
    "blocks": ["autocomplete-result-list.v2"],
    "props": {
      "openAutocompleteOnFocus": true
    }
  }
}
```

#### The `autocomplete-result-list.v2` props

| Prop name                     | Type                    | Description                                                                | Default value |
| ----------------------------- | ----------------------- | ----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| `maxTopSearches`              | `number`                | Maximum number of items in the top searches list.                | `10`          |
| `maxHistory`                  | `number`                | Maximum number of items in the search history list.                                                            | `5`           |
| `maxSuggestedProducts`        | `number`                | Maximum number of items in the suggested products list.                                                      | `3`           |
| `maxSuggestedTerms`           | `number`                | Maximum number of items in the suggested terms list.                                                                 | `3`           |
| `autocompleteWidth`           | `number`                | Autocomplete list width (in percent). The value must be between `0` and `100`.                                | `undefined`   |
| `productLayout`               | `enum`                  | Defines the suggested products list layout when rendered. Possible values are `HORIZONTAL` and `VERTICAL`.     | `undefined`   |
| `hideTitles`                  | `boolean`               | Defines whether all component titles are hidden when rendered (`true`) or not (`false`).              | `false`       |
| `hideUnavailableItems`                  | `boolean`               | Defines whether the autocomplete should hide unavailable items (`true`) or not (`false`).             | `false`       |
| `historyFirst`                | `boolean`               | Defines whether the search history list should be prioritized over the other lists (`true`) or not (`false`).                                                          | `false`       |
| `customBreakpoints`           | `object`                | Defines a maximum number of suggested products by breakpoints. Possible values are `md`, `lg` or `xlg`.                                                           | -             |
| `simulationBehavior`          | `"skip"` or `"default"` | If you want faster searches and do not care about most up to date prices and promotions, use `"skip"` value.     | `default`     |
| `HorizontalProductSummary`          | `product-summary` block | By default, the mobile autocomplete uses the `CustomListItem` component to render the suggested products with a horizontal layout. But if you send a `product-summary` block here, it will render your customized Product Summary component. Read our documentation of [how to build a horizontal Product Summary](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-building-a-horizontal-product-summary) component.                            | `undefined`     |

##### The `customBreakpoints` object

| Prop name | Type     | Description                                                                    | Default value |
| --------- | -------- | ------------------------------------------------------------------------------ | ------------- |
| `md`      | `object` | Defines the maximum number of suggested products for the `md` breakpoint.      | `undefined`   |
| `lg`      | `object` | Defines the the maximum number of suggested products for the `lg` breakpoint.  | `undefined`   |
| `xlg`     | `object` | Defines the the maximum number of suggested products for the `xlg` breakpoint. | `undefined`   |

##### The `md`, `lg` and `xlg` objects

| Prop name              | Type     | Description                           | Default value |
| ---------------------- | -------- | ------------------------------------- | ------------- |
| `width`                | `number` | Breakpoint minimum width.             | `undefined`   |
| `maxSuggestedProducts` | `number` | Maximum number of suggested products. | `undefined`   |

The `autocomplete-result-list.v2` block also allows you to add a list of child blocks onto it. You can declare a theme block of your choosing and have it rendered among the autocomplete features, for example:

```json
{
  "autocomplete-result-list.v2": {
    "blocks": ["product-summary"]
  }
}
```

Now, you can add the last three search blocks: `search-banner`, `did-you-mean` and `search-suggestions`.

Those blocks, differently from `autocomplete-result-list.v2`, need to be added under the `search-result-layout.desktop` or the `search-result-layout.mobile` blocks, according to the Search Results block hierarchy.

Once added, these can be declared using their respective props for their configuration, for example:

```json
{
  "search-result-layout.desktop": {
    "children": [
      "flex-layout.row#did-you-mean",
      "flex-layout.row#suggestion",
      "flex-layout.row#banner-one",
      "flex-layout.row#result"
    ],
    "props": {
      "pagination": "show-more",
      "preventRouteChange": true,
      "mobileLayout": {
        "mode1": "small",
        "mode2": "normal"
      }
    }
  },

  "flex-layout.row#did-you-mean": {
    "children": ["did-you-mean"]
  },
  "flex-layout.row#suggestion": {
    "children": ["search-suggestions"]
  },
  "flex-layout.row#banner-one": {
    "children": ["search-banner#one"]
  },

  "search-banner#one": {
    "props": {
      "area": "one",
      "blockClass": "myBanner",
      "horizontalAlignment": "center"
    }
  }
}
```

#### The `search-banner` props

| Prop name             | Type     | Description                                                                                                                      | Default value |
| --------------------- | -------- | -------------------------------------------------------------------------------------------------------------------------------- | ------------- |
| `area`                | `string` | Area of ​​the store where the banner will be displayed. It needs to match the predefined area value in the banner setup.         | `undefined`   |
| `blockClass`          | `string` | Unique block ID to be used in [CSS customization](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-using-css-handles-for-store-customization) | `undefined`   |
| `horizontalAlignment` | `string` | Defines the banner horizontal alignment. Possible values are `left`, `center` or `right`.                                        | `center`      |

## Modus Operandi

The Search app is responsible for offering blocks that when rendered as components will improve the user's search experience in stores where the VTEX Intelligent Search engine is already supported.

These components use `_q` as the query-string for the search term, meaning that if you wish to track the searches of your users in these components you'll need to add the `_q` query-string to the store's Google Analytics.

Find out how to do this by accessing our [Google Analytics search tracking](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-setting-up-google-analytics-search-tracking) documentation.

## Customization

In order to apply CSS customizations in this and other blocks, follow the instructions given in the recipe on [Using CSS Handles for store customization](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-using-css-handles-for-store-customization).

| CSS Handles             |
| ----------------------- |
| `searchBanner`          |
| `didYouMeanPrefix`      |
| `didYouMeanTerm`        |
| `suggestionsList`       |
| `suggestionsListItem`   |
| `suggestionsListLink`   |
| `itemListSubItemLink`   |
| `itemListLink`          |
| `itemListLinkTitle`     |
