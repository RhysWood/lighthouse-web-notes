# Objects

## Key Value Pairs
- Keys are always strings
- Each key is unique (can only occur once in the object)
- Each key is associated with exactly one value. (Note that technically, an array or another object - would count as "one value" here, even though they contain other values.)

When writing out object literals, like { myKey: "some value" }, the key is always interpreted as a literal string, even if it's unquoted. It's only necessary to use quotes around the key if the key contains spaces, hyphens or periods. For instance: { "my-hyphenated-key": "some value" }.

By convention, we omit the quotes around keys in string literals whenever we can. If the key is a valid variable name, then we don't have to include quotes

## Looping Objects
JavaScript objects, {key: value}, themselves are not iterable. Instead we need to use a "For In" Loop. EG: 

``` javascript 
var planetMoons = {
  mercury: 0,
  venus: 0,
  earth: 1,
  mars: 2,
  jupiter: 67,
  saturn: 62,
  uranus: 27,
  neptune: 14
};

for (var planet in planetMoons) {
  var numberOfMoons = planetMoons[planet];
  console.log("Planet: " + planet + ", # of Moons: "+ numberOfMoons);
}
```
The key is available to us within the scope of the loop; in the above example it is the planet variable. The variable planet iterates over each key ("mercury", "venus", ...) using the for-loop.

objects can sometimes have properties that they inherit from their prototype chain as well as method names. An additional filtering step is sometimes necessary:

``` javascript
for (var planet in planetMoons) {
  // additional filter for object properties:
  if (planetMoons.hasOwnProperty(planet)) {
    //  ...
  }
}
```