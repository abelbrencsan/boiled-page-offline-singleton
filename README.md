# Boiled Page offline singleton

Offline SCSS singleton for Boiled Page frontend framework. It is intended to show an alert on the top of the page when user has no internet connection. It uses `offline` and `online` JavaScript events for detection.

## Install

Place `_offline.scss` file to `/assets/css/singletons` directory, and add its path to singleton block in `assets/css/app.scss` file.

## Usage

### Classes

Class name | Description | Example
---------- | ----------- | -------
`offline` | Applies offline. | `<div class="offline"></div>`

### Examples

#### Example 1

The following example shows an alert ont the top of the page when user is offline.

```html
<div class="offline">You are offline! Please connect to a network!</div>
```

Place the following code inside assets/js/app.js to check user is online, add `is-offline` class to body if not.

```js
// Check user is online
if (!navigator.onLine) {
  document.body.classList.add('is-offline');
}
window.addEventListener('offline', function(event) {
  document.body.classList.add('is-offline');
});
window.addEventListener('online', function(event) {
  document.body.classList.remove('is-offline');
});
```
