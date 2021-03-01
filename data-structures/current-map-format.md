---
description: Song sheet or mapping format
---

# Current Map Format

## Map format

JSON array of note objects

### Note object

```javascript
{
  "t": float, // time: note start time in seconds
  "k": str,   // key: single or combination of 'a','s','d','f',' ','j','k','l',';'
  "h": {      // hold: hold key object, optional if key or part of the key is a hold key
    "[str]": float //[str]: hold key end time in seconds, keys like d,f,j,k
  }
}
```

## Example mapping format

```javascript
[
   {
      "t":44.59,
      "k":"j"
   },
   {
      "t":45.054,
      "k":"f"
   },
   {
      "t":45.529,
      "k":"j"
   },
   {
      "t":46.014,
      "k":"dk"
   },
   {
      "t":53.564,
      "k":"k",
      "h":{
         "k":54.400999999999996
      }
   },
   {
      "t":54.444,
      "k":"f",
      "h":{
         "f":55.297
      }
   },
   {
      "t":55.356,
      "k":"j",
      "h":{
         "j":56.209
      }
   },
   {
      "t":56.278,
      "k":"dj",
      "h":{
         "d":57.153000000000006,
         "j":59.126
      }
   },
   {
      "t":57.281,
      "k":"k",
      "h":{
         "k":58.065
      }
   },
   {
      "t":58.236,
      "k":"f",
      "h":{
         "f":58.98233333333333
      }
   },
   {
      "t":59.094,
      "k":"dk",
      "h":{
         "d":59.81433333333334,
         "k":"59.81433333333334"
      }
   },
   {
      "t":59.985,
      "k":"jf",
      "h":{
         "j":60.67833333333333,
         "f":"60.67833333333333"
      }
   },
   {
      "t":65.756,
      "k":"d"
   },
   {
      "t":76.721,
      "k":"k"
   },
   {
      "t":76.977,
      "k":"d"
   },
   {
      "t":77.34,
      "k":"j"
   },
   {
      "t":77.665,
      "k":"f",
      "h":{
         "f":78.40633333333332
      }
   },
   {
      "t":78.785,
      "k":"k"
   },
   {
      "t":79.158,
      "k":"j"
   },
   {
      "t":79.441,
      "k":"kd",
      "h":{
         "d":80.13433333333333
      }
   },
   {
      "t":80.465,
      "k":"d"
   },
]
```

