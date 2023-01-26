---
title: "Speech to Text Search"
slug: "vtexarg-speech-to-text"
excerpt: "vtexarg.speech-to-text@1.0.10"
hidden: false
createdAt: "2021-07-28T15:17:51.703Z"
updatedAt: "2022-11-03T17:57:01.905Z"
---

The `speech-to-text` app uses Google Chrome language processing to listen to the user's microphone and convert speech-to-text. The recognized text is then used to redirect the user to the corresponding search page.

![speechlow](https://cdn.jsdelivr.net/gh/vtexdocs/dev-portal-content@main/images/vtexarg-speech-to-text-0.gif)

## Configuration

1. Add the `vtexarg.speech-to-text` app to your theme's **peer dependency** in the `manifest.json` file.
2. Add the `text-speech` block to the desired theme template or inside another block. For example:

```
  "flex-layout.col#text-speech": {
    "children": [
      "speech-to-text"
    ]
  },
```

3. Then, declare the `speech-to-text` block using the props stated in the [Props](#props) table. For example

```
 "speech-to-text": {
    "props": {
      "lang": "es-ES",
      "iconHeight": "20px",
      "iconWidth": "20px",
      "imgSrc": "https://upload.wikimedia.org/wikipedia/commons/a/a7/Font_Awesome_5_solid_microphone.svg"
    }
  }
```

## Props

| Prop name    | Type            | Description    | Default value                                                                                                                               |
| ------------ | --------------- | --------------------------------------------------------------------------------------------------------------------------------------------- | ---------- |
| `lang`      | `enum`       | Language used by the Google Chrome NLP API.         | `en-EN`        |
| `iconHeight`      | `string`       | Icon height in px.         | `20px`        |
| `iconWidth`      | `string`       | Icon width in px.         | `20px`        |
| `imgSrc`      | `string`       | URL of the source image.         | `none`        |

## Customization

To apply CSS customizations in this and other blocks, follow the [Using CSS handles for store customization](https://developers.vtex.com/vtex-developer-docs/docs/vtex-io-documentation-using-css-handles-for-store-customization) guide.

| CSS Handles |
| ----------- |
| `audioSearchContainer` |
| `audioSearchImg` |
| `audioSearchImgRecordingState` |
