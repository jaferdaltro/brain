```
// Simulate going offline
Object.defineProperty(navigator, 'onLine', {
  writable: true,
  value: false
});

// Dispatch offline event
window.dispatchEvent(new Event('offline'));
```


```
// Simulate going back online

Object.defineProperty(navigator, 'onLine', {
  writable: true,
  value: true
});

window.dispatchEvent(new Event('online'));
```