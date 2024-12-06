# Apify Push Actor GitHub Action

A GitHub action that lets you push an Actor to the Apify platform, for example after every release.

## Inputs

**token**: The Apify token that should be used to authenticate the push operation. See the [Apify integration docs](https://docs.apify.com/platform/integrations/api#api-token) for instructions on how to find it.

**build-tag**: Build tag to be applied to the successful Actor build. By default, it is taken from the ".actor/actor.json" file.

**version**: Actor version number to which the files should be pushed. By default, it is taken from the ".actor/actor.json" file.

**

## Example usage

```yaml
jobs:
  push_to_apify:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout sources
        uses: actions/checkout@v4

      - name: Set up node.js
        uses: actions/setup-node@v4
        with:
          node-version: 22

      - name: Push to Apify
        uses: apify/push-actor-action@master
        with:
          token: ${{ secrets.APIFY_TOKEN }}
```
