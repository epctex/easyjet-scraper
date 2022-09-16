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

The input of this scraper should be JSON containing. Required fields are:

| Field            | Type    | Description                                                                                                                                                                                                                                                     |
| ---------------- | ------- | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- |
| mode             | String  | Mode for the actor. It can be either `ROUND` for Round trip or `ONEWAY` for One way trips.                                                                                                                                                                      |
| arrival           | String  | 3-letter arrival airport code. Ex: VIE                                                                                                                                                                                                                           |
| departure      | String  | 3-letter departure airport code. Ex: VIE                                                                                                                                                                                                                      |
| departureDate    | String  | Date for departure. Should be in the format of `YYYY-MM-DD`. Ex: 2021-02-21                                                                                                                                                                                     |
| departureDate    | String  | Date for return. It is required for Round trips. Should be in the format of `YYYY-MM-DD`. Ex: 2021-02-21                                                                                                                                                        |
| adults           | Integer | Number of adults that will be included on the flight. Minimum number is 1.                                                                                                                                                                                      |
| children         | Integer | (optional) Number of children (2-11 years old) that will be included on the flight.                                                                                                                                                                             |
| infants          | Integer | (optional) (optional) Number of teens (Under 2 years old) that will be included on the flight.                                                                                                                                                                  |
| maxItems         | Integer | (optional) You can limit scraped products. Default is `Infinite`.                                                                                                                                                                                               |
| proxy            | Object  | Proxy configuration                                                                                                                                                                                                                                             |
This solution requires the use of **Proxy servers**, either your own proxy servers or you can use <a href="https://www.apify.com/docs/proxy">Apify Proxy</a>.

### Compute Unit Consumption

The actor optimized to run in a very fast manner and scrape the flights in the most performant way. Therefore, it forefronts all flight result requests. If actor doesn't block very often it'll scrape 10 flights in 3 seconds with ~0.005-0.01 compute units.

### Easyjet Scraper Input example

```json
{
  "CarrierCode": "EJU",
  "FlightNumber": 4358,
  "SegmentId": "20220810AJALYS4358",
  "DepartureIata": "AJA",
  "ArrivalIata": "LYS",
  "LocalDepartureTime": "2022-08-10T12:15:00",
  "LocalArrivalTime": "2022-08-10T13:25:00",
  "FlightFares": [
    {
      "FareType": "Standard",
      "SeatsAvailable": 9,
      "LowestFareSeatsAvailable": 4,
      "Prices": {
        "Adult": {
          "Price": 42.22,
          "PriceWithDebitCard": 42.22,
          "PriceWithCreditCard": 42.22
        }
      },
      "FlightIdentification": "UlAwMUJCQkIzYk44QkJCQkJCQkJBSkFCQkJCNi5MWVNCNC5FVVJCQkJCUy5FVVJCTjA3MjAyMi0wOC0xMCAxMjoxNTowMFFK"
    }
  ],
  "PromotionalFareType": "None",
  "FlightTaxes": {
    "TaxAmount": 27.23,
    "ApplyApdRules": false
  },
  "IsDisrupted": false
}
```
