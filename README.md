# tag-matcher [![Build Status](https://travis-ci.org/Colum-SMA-Dev/tag-matcher.svg?branch=master)](https://travis-ci.org/Colum-SMA-Dev/tag-matcher)
A boolean tag matching library.  Interface is similar to regexs, you make a matcher with a query, and then call match() on it passing it something to match.  Tags must be passed to match() as an array of tags.

Example usage:

```
// verifying tag arrays
var matcher = new TagMatcher('fish OR bird');

console.log(matcher.match(['fish', 'walrus'])); // true
console.log(matcher.match(['magpie', 'bird'])); // true
console.log(matcher.match(['lion', 'walrus'])); // false


// comparing matchers
var sameMatcher = new TagMatcher('fish OR bird');
var differentMatcher = new TagMatcher('(apple AND banana) OR fish');

console.log(matcher.equalTo(sameMatcher)); // true
console.log(matcher.equalTo(differentMatcher)); // false
```

=== Boolean operators implemented

- OR
- AND
- parenthesis of infinite depth

Check out the [test cases for match()](test/test-match.js) for more details.
