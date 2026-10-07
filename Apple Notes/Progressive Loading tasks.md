---
apple-notes-id: 4F80C3F1-1A98-4C73-A3EC-95FC48A12CE6
---
Essa parece ser pra ver se está no inicial state:
O SKELETON aparecera quando a FF tiver true + inicial state

```
shouldShowLoadingSkeleton
isProgressiveLoadingEnabled - Feature do PL
hasDeviceData === INITIAL_STATE
```

Inserir nesse skeleton a strategy ‘loading’ ou ‘navigate-away’



—

```
  const shouldShowLoadingSkeleton =
    (isProgressiveLoadingEnabled && strategy === 'loading') ||
    (strategy === 'navigate-away' &&
      hasDeviceData === DeviceDataState.INITIAL_STATE &&
      (!isPopularFeaturesEnabled || !isProgressiveLoadingEnabled));
```