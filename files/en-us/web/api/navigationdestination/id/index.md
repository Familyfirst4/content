---
title: "NavigationDestination: id property"
short-title: id
slug: Web/API/NavigationDestination/id
page-type: web-api-instance-property
status:
  - experimental
browser-compat: api.NavigationDestination.id
---

{{APIRef("Navigation API")}}{{SeeCompatTable}}

The **`id`** read-only property of the
{{domxref("NavigationDestination")}} interface returns the {{domxref("NavigationHistoryEntry.id", "id")}} value of the destination {{domxref("NavigationHistoryEntry")}} if the {{domxref("NavigateEvent.navigationType")}} is `traverse`, or an empty string otherwise.

The `id` is a unique, UA-generated value that always represents the history entry, useful to correlate a history entry with an external resource such as a storage cache.

## Value

A string representing the `id` of the destination {{domxref("NavigationHistoryEntry")}}, or an empty string.

## Examples

```js
navigation.addEventListener("navigate", (event) => {
  console.log(event.destination.id);
});
```

## Specifications

{{Specifications}}

## Browser compatibility

{{Compat}}

## See also

- [Modern client-side routing: the Navigation API](https://developer.chrome.com/docs/web-platform/navigation-api/)
- [Navigation API explainer](https://github.com/WICG/navigation-api/blob/main/README.md)
