# Actor - Easyjet Scraper

## Easyjet scraper

Since Easyjet doesn't provide an good API, this actor should help you to retrieve data from it.

The Easyjet data scraper supports the following features:

-   Scrape round trip - you can scrape a complete round trip with departure and return dates.
-   Scrape one way trip - you can scrape an one way trip with just providing the departure date
-   Scrape with multiple people options - You can scrape Easyjet with Adults, Teens, Children and Infants options

## Bugs, fixes, updates and changelog

This scraper is under active development. If you have any feature requests you can create an issue from [here](https://github.com/epctex/easyjet-scraper/issues).

## Input Parameters

The input of this scraper should be JSON containing. Possible fields are:

- `mode`: (Required) (String) Mode for the actor. It can be either `ROUND` for Round trip or `ONEWAY` for One way trips.

- `arrival`: (Required) (String) 3-letter arrival airport code. Ex: VIE.

- `departure`: (Required) (String) 3-letter departure airport code. Ex: VIE.

- `departureDate`: (Required) (String) Date for departure. Should be in the format of `YYYY-MM-DD`. Ex: 2021-02-21.

- `returnDate`: (Optional) (String) Date for return. It is required for Round trips. Should be in the format of `YYYY-MM-DD`. Ex: 2021-02-21.

- `adults`: (Required) (Number) Number of adults that will be included on the flight. Minimum number is 1.

- `infants`: (Optional) (Number) Number of teens (Under 2 years old) that will be included on the flight.

- `children`: (Optional) (Number) Number of children (2-11 years old) that will be included on the flight.

- `maxItems`: (Optional) (Number) You can limit scraped items. This should be useful when you search through the big lists or search results.

- `proxy`: (Required) (Proxy Object) Proxy configuration.

This solution requires the use of **Proxy servers**, either your own proxy servers or you can use <a href="https://www.apify.com/docs/proxy">Apify Proxy</a>.

### Compute Unit Consumption

The actor optimized to run in a very fast manner and scrape the flights in the most performant way. Therefore, it forefronts all flight result requests. If actor doesn't block very often it'll scrape 10 flights in 3 seconds with ~0.005-0.01 compute units.

### Easyjet Scraper Input example

```json
{
  "adults": 1,
  "arrival": "AMS",
  "departure": "LPL",
  "departureDate": "2023-01-06",
  "mode": "ROUND",
  "proxy": {
    "useApifyProxy": true
  },
  "returnDate": "2023-02-08"
}
```

### Easyjet Scraper Output example

```json
https://api.apify.com/v2/datasets/oKobkcRCgfeIuiNKE/items?clean=true&format=json
```

## Contact
Please visit us through [epctex.com](https://epctex.com) to see all the products that is available for you. If you are looking for any custom integration or so, please reach out to us through the chat box in [epctex.com](https://epctex.com). In need of support? [devops@epctex.com](mailto:devops@epctex.com) is at your service.
