---
title: privacy.services
slug: Mozilla/Add-ons/WebExtensions/API/privacy/services
page-type: webextension-api-property
browser-compat: webextensions.api.privacy.services
sidebar: addonsidebar
---

The `privacy.services` property contains privacy-related settings controlling services offered by the browser or by third parties. Each property is a {{WebExtAPIRef("types.BrowserSetting")}} object.

## Properties

- `passwordSavingEnabled`
  - : A {{WebExtAPIRef("types.BrowserSetting")}} object whose underlying value is a boolean. If `true`, the browser's password manager will offer to store passwords when the user enters them. Defaults to `true`.

## Examples

Disable the password manager if possible.

```js
function onSet(result) {
  if (result) {
    console.log("success");
  } else {
    console.log("failure");
  }
}

let getting = browser.privacy.services.passwordSavingEnabled.get({});
getting.then((got) => {
  console.log(got.value);
  if (
    got.levelOfControl === "controlled_by_this_extension" ||
    got.levelOfControl === "controllable_by_this_extension"
  ) {
    let setting = browser.privacy.services.passwordSavingEnabled.set({
      value: false,
    });
    setting.then(onSet);
  } else {
    console.log("Not able to set passwordSavingEnabled");
  }
});
```

{{WebExtExamples}}

## Browser compatibility

{{Compat}}

> [!NOTE]
> This API is based on Chromium's [`chrome.privacy`](https://developer.chrome.com/docs/extensions/reference/api/privacy) API.
