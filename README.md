# pizza-operator

pizza-operator orders pizza for you. This repo is based on an idea by @teemow.

## Usage

You need to provide a provider-specific ConfigMap for configuring your Pizza (for details refer to respective provider documentation). For payments our implementation requires referencing a secret containing your payments credentials.

```
apiVersion: food.giantswarm.io/v1alpha1
kind: Pizza
metadata:
  name: my-favorite-pizza
spec:
  provider: Vapiano
  ToppingsProviderConfig:
    name: my-pizza-config
    namespace: puja      
  payment:
    type: credit
    secret:
      name: pujas-credit-card
      namespace: puja
```

## Code

pizza-operator is written using [nocode](https://github.com/kelseyhightower/nocode) and thus compatible with all kinds of Pizza providers and extendable to non-pizza delivery items like Sushi and Chinese takeout.

## Inspiration

https://ndmckinley.github.io/terraform-provider-dominos/
