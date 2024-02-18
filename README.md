# Run multiple tests sequentially in jest

The "each" method of jest is able execute many tests in a row.

This approach allows developers to use seed data to determine how functions can behave and produce the desired results.

Cases are passed as an array argument to the "each" method. As a result, all tests run individually.


```js
// A sample method to check if the result of adding numbers is odd
const isSumResultOdd = (a, b) => (a + b) % 2 !== 0;

// The result expected to determine the isSumResult by passing value in the bulk tests
const bulkTests = test.each([
  [5, 2, true],
  [3, 4, true],
  [2, 2, true],
]);

// All tests are run sequentially
bulkTests("Adding %i and %i should be odd is %s", (a, b, expected) => {
  expect(isSumResultOdd(a, b)).toBe(expected);
});

// Error expression: Adding 2 and 2 should be odd is true
// The result for [2, 2, true] isn't expected to true
```
