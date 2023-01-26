---
title: "My Account Commons"
slug: "vtex-my-account-commons"
excerpt: "vtex.my-account-commons@1.5.2"
hidden: false
createdAt: "2020-06-03T15:19:30.129Z"
updatedAt: "2020-09-10T20:04:22.179Z"
---

My Account Commons is a bundle of canonical components that can be used to create new tabs to be inserted on the `vtex.my-account` app.

DISCLAIMER: In order to this components work, they need to be children of `vtex.my-account` app.

To import it into your code:

```js
import {
  ContentWrapper,
  BaseLoading,
  GenericError,
} from 'vtex.my-account-commons'
```

## Usages

### ContentWrapper

You can use it in your code like a React component with the jsx tag: `<ContentWrapper>`.

```jsx
<ContentWrapper
  namespace="my-custom-page"
  title={`${orderTitle} ${orderNumber}`}
  backButton={backButton}>
  {({ handleError }) => children}
</ContentWrapper>
```

| Prop name            | Type      | Description                                                                  |
| -------------------- | --------- | ---------------------------------------------------------------------------- |
| `title`              | `String`  | The string that will appear on the page title.                               |
| `titleId`            | `String`  | Intl message id that will be translated and inserted on the page title.      |
| `backbutton.title`   | `String`  | The string that will appear as a message on the backbutton.                  |
| `backbutton.titleId` | `String`  | Intl message id that will be translated and inserted as the go back message. |
| `backbutton.path`    | `String!` | Location which the user will be lead to when hit the backbutton.             |
| `headerContent`      | `node`    | JSX that wil be inserted as children of the `vtex.style-guide/PageHeader`.   |
| `namespace`          | `String!` | Css namespace that will be added to the page body.                           |

The `ContentWrapper` uses the render prop pattern and returns to its children an object with the following props:

#### Render prop

| Prop name    | Type       | Description                                                             |
| ------------ | ---------- | ----------------------------------------------------------------------- |
| `handlError` | `Function` | Function that will be called when the user dismisses the error message. |

### BaseLoading

This component should be used to implement your own Loader, it analyses the result of a graphql query and displays
the loader Skeleton or an error message if any error occurs with retry option to call refetch on the query.

```jsx
<BaseLoading queryData={data} headerConfig={object}>
  {children}
</BaseLoading>
```

| Prop name      | Type            | Description                                                                                                       |
| -------------- | --------------- | ----------------------------------------------------------------------------------------------------------------- |
| `queryData`    | `QueryResult`   | Apollo Graphql query result.                                                                                      |
| `headerConfig` | `ContentWProps` | The props that will be passed to the `ContentWrapper`.                                                            |
| `nameSpace`    | `String`        | The name space prop that will be passed to the `ContentWrapper`. `vtex-base-loading` is applied if none is passed |
| `parseError`   | `Function`      | Function that parses the graphql error and returns a messageId.                                                   |

### GenericError

A wrapper for the `vtex.styleguide/Alert` component.

```jsx
<GenericError onDismiss={handleError} errorId={error} />
```

| Prop name   | Type       | Description                                                          |
| ----------- | ---------- | -------------------------------------------------------------------- |
| `error`     | `String`   | The error message that will be displayed on the `Alert`.             |
| `errorId`   | `String`   | Intl message id that will be translated and inserted on the `Alert`. |
| `onDismiss` | `Function` | Function that will be called when the user hits the close button.    |

### Disclaimer about react/Router.js file

Read carefully the instructions within the file before editing it.