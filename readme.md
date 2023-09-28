# Appwrite Zipcode Lookup

One-file function to lookup zipcodes & regions in Germany 🥨.

## Live demo

There's a live version for demo purposes on the appwrite cloud: https://6515b4f4bd2d9aaff67c.appwrite.global/

> Please do not use this for productive purposes, I might take this one down anytime

Give it a try ([best used with a JSON formatter](https://chrome.google.com/webstore/detail/json-formatter/bcjindcccaagfpapjjmafapmmgkkhgoa))

- List all places for Northrhine-Westfalia: [?state-code=NW](https://6515b4f4bd2d9aaff67c.appwrite.global/?state-code=NW)
- Find the 5 closest places around Duesseldorf: [?langitude=51.2216&longitude=6.7897&max-entries=5](https://6515b4f4bd2d9aaff67c.appwrite.global/?langitude=51.2216&longitude=6.7897&max-entries=5)
- Get the closes place 15 kilometers around this random place in NW (default-distance=5 will be empty): [/?langitude=51.0497&longitude=6.7648&distance=15](https://6515b4f4bd2d9aaff67c.appwrite.global/?langitude=51.0497&longitude=6.7648&distance=15)
- [Proof that Bielefeld exists](https://en.wikipedia.org/wiki/Bielefeld_conspiracy): [/?zipcode=33619](https://6515b4f4bd2d9aaff67c.appwrite.global/?zipcode=33619)

## Deployment

1. Create a new appwrite function
2. Paste the content of `main.js` into your function (Note: all available Zipcodes are part of this file)
3. Deploy your function and start querying!

## Querying

After you have deployed your function, there are a few ways to use this function:

1. Query by ZIP-Code directly (e.g. `?zipcode=41540`)
2. Query by State code (e.g. `?state-code=BW`)
3. Query by langitude & latitude (e.g. `?latitude=52.0333&longitude=8.5333`.)

There are a few optional parameters you can use on top on using the `long-lat` approach.

> Note: Without specifying longitude and latitude, these will throw an error

1. `&max-entries=<value>` <- specify the count of returned entries (default: 1)
2. `&distance=<value>` <- specify the max. distance for which entries are returned in KM (default: 5)

---

## Attributions

- Zipcodes for Germany where sourced from [zauberware/postal-codes-json-xml-csv](https://github.com/zauberware/postal-codes-json-xml-csv) repository and are modified during runtime by calculating the distance from the user's input using Harvestine calculation.