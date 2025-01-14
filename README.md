# Apify Push Actor GitHub Action

## What is Apify?

[Apify](https://apify.com/) is a full-stack web scraping and automation platform where developers can build, deploy, and publish serverless microapps called Actors.

## What does Apify Push Actor GitHub Action do?

This GitHub action lets you push an Actor to the Apify platform, e.g. after every release. You can even easily make a beta release after each commit.

## Inputs

**token** (required): The Apify token that should be used to authenticate the push operation. See the [Apify integration docs](https://docs.apify.com/platform/integrations/api#api-token) for instructions on how to find it.

**actor-id** (optional): Name or ID of the Actor to push (e.g. "apify/hello-world" or "E2jjCZBezvAZnX8Rb"). If not provided, the command will create or modify the Actor with the name specified in ".actor/actor.json" file. 

**build-tag** (optional): Build tag to be applied to the successful Actor build. By default, it is taken from the ".actor/actor.json" file.

**version** (optional): Actor version number to which the files should be pushed. By default, it is taken from the ".actor/actor.json" file.

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

## Examples of top Actors on Apify Store
There are thousands of pre-built Actors on Apify Store. Check out some of the most popular:
- [Website Content Crawler](https://apify.com/apify/website-content-crawler): Crawl websites and extract text content to feed AI models, LLM applications, vector databases, or RAG pipelines.
- [Google Search Results Scraper](https://apify.com/apify/google-search-scraper): Extract organic and paid results, AI overviews, ads, queries, People Also Ask, prices, reviews, like a Google SERP API. 
- [Instagram Scraper](https://apify.com/apify/instagram-scraper): Scrape and download Instagram posts, profiles, places, hashtags, photos, and comments. 
- [Google Maps Email Extractor](https://apify.com/lukaskrivka/google-maps-with-contact-details): Scrape websites of Google Maps places for contact details and get email addresses, website, location, address, zipcode, phone number, social media links. 

## Additional resources
- Join 9,000+ web scraping and automation devs on the [Apify Discord](https://discord.com/invite/jyEM2PRvMU).
- [Apify documentation](https://docs.apify.com/): Platform guides and API references.
- [Apify open source](https://docs.apify.com/open-source): Apify's open-source libraries, including [Crawlee](https://crawlee.dev/), a web scraping and browser automation library for Node.js and Python.
- [Monetize your code](https://apify.com/partners/actor-developers): Share your Actors with the world and earn revenue whenever anyone uses them.
