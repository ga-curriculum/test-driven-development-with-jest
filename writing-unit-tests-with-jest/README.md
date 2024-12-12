<h1>
  <span class="headline">Test Driven Development with Jest</span>
  <span class="subhead">Writing Unit Tests with Jest</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to write and group unit tests for JavaScript functions using Jest, leveraging `describe`, `it`/`test`, and matchers like `expect().toBe()`.

## Writing tests in Jest: `describe`, `it`, and `test`

Writing tests in Jest is straightforward and helps ensure your code behaves as expected.

### Let's start with an example

Imagine we have a simple function called `add`:

```js
function add(num1, num2) {
  return num1 + num2;
}
```

To test this function, we’ll create a dedicated file for our tests. Jest provides a way to group related tests using the `describe` keyword. For example, if we’re testing multiple scenarios (ex: success and failure cases) for the same function, we can wrap them in a `describe` block:

```js
describe('the add function', () => {
  // Write your tests inside this block
});
```

### How `describe` works

- **First argument**: A string that describes what this group of tests is testing. This appears in the console when the tests run, helping you identify each group.
- **Second argument**: A function that contains all the tests for this group.

### Writing individual tests

Within a `describe` block, we define individual tests using either the `test` or `it` keyword. According to the [Jest documentation](https://jestjs.io/), `it` is an alias for `test`, so they are interchangeable. Use the one that makes your tests more human readable.

Here’s a basic test using `test`:

```js
test('it adds 1 and 3 to equal 4', () => {
  expect(add(1, 3)).toBe(4);
});
```

Or using the `it` alias:

```js
it('adds 1 and 3 to equal 4', () => {
  expect(add(1, 3)).toBe(4);
});
```

### Making Assertions

To assert that a test passes, we use [expect()](https://jestjs.io/docs/expect) combined with a matcher, like [toBe()](https://jestjs.io/docs/expect#tobevalue). Jest provides many matchers for different scenarios, which you can explore in the [Jest documentation](https://jestjs.io/docs/using-matchers).

## Let’s practice

1. In your `test-driven-development-with-jest` directory, create a file called `functions.test.js`. This will hold your tests.

We’ll write tests for a function named `addTwoNumbers`.

The function should:

1. Accept two arguments (numbers).
2. Return an error message if one or both arguments are not numbers.
3. Return the sum if both arguments are numbers.

Here’s how the tests might look:

```js
describe('addTwoNumbers', () => {
  it('adds two numbers together', () => {
    expect(addTwoNumbers(1, 2)).toBe(3);
    expect(addTwoNumbers(1.5, 2)).toBe(3.5);
  });

  it('returns an error message if incorrect data types are passed', () => {
    expect(addTwoNumbers(1, '1')).toBe(numbersDataTypeError);
    expect(addTwoNumbers(1, {})).toBe(numbersDataTypeError);
    expect(addTwoNumbers([], {})).toBe(numbersDataTypeError);
  });
});
```

Copy and paste the code above into your `functions.test.js` file.

### Write the function

Now we need to write the actual `addTwoNumbers` function.

1. Create a new file called `functions.js`.
2. Write the function and ensure it matches the test requirements.
3. Export the function so it can be used in the tests.
4. You'll also need to create a variable for the `numbersDataTypeError` and add it to the exports.

Your file might look like this:

```js
const numbersDataTypeError =
  'Incorrect data types passed to function. Types must be number';

function addTwoNumbers(num1, num2) {
  // complete the test function
}

module.exports = { addTwoNumbers, numbersDataTypeError };
```

Now import the function and the error message into your `functions.test.js` file:

```js
const { addTwoNumbers, numbersDataTypeError } = require('./functions');
```

## Run Your Tests

When you think your function will pass the tests, run the following command in your terminal:

```sh
npm run test
```

Jest will execute your tests and provide feedback on whether they pass or fail in the terminal.
