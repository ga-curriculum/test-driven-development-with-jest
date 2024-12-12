<h1>
  <span class="headline">Test Driven Development with Jest</span>
  <span class="subhead">Skipping Tests</span>
</h1>

**Learning Objective:** By the end of this lesson, students will be able to identify and apply techniques to skip tests in Jest, effectively managing test execution during the development process.

## Skipping tests

When working on a test-driven development (TDD) project, it’s completely normal to have failing tests, especially in the early stages. While these failures can guide your development, there may be times when you want to temporarily focus on specific parts of your code without being distracted by unrelated test failures.

Jest makes it easy to **skip tests**. By adding an `x` in front of `describe`, `test`, or `it`, you can tell Jest to skip running those specific tests or test groups.

### Skipping all tests in a group

If you want to skip an entire group of related tests, you can prepend an `x` to the `describe` block. This will skip all tests inside that block.

For example:

```js
xdescribe('the add function', () => {
  // All tests inside this block will be skipped.
  it('adds two numbers together', () => {
    expect(add(1, 2)).toBe(3);
  });

  it('throws an error when passed invalid input', () => {
    expect(() => add(1, 'two')).toThrow();
  });
});
```

By skipping the `describe` block, none of the tests inside it will run. This can be helpful when you’re not ready to debug or fix an entire set of tests.

### Skipping a specific test

If you only want to skip an individual test, you can prepend an `x` to the `test` or `it` function. For example:

```js
describe('addTwoNumbers', () => {
  it('adds two numbers together', () => {
    expect(addTwoNumbers(1, 2)).toBe(3);
    expect(addTwoNumbers(1.5, 2)).toBe(3.5);
  });

  xit('returns an error message if incorrect data types are passed', () => {
    expect(addTwoNumbers(1, '1')).toBe(numbersDataTypeError);
    expect(addTwoNumbers(1, {})).toBe(numbersDataTypeError);
    expect(addTwoNumbers([], {})).toBe(numbersDataTypeError);
  });
});
```

In this example:

- The first test (`adds two numbers together`) will run as usual.
- The second test (`returns an error message if incorrect data types are passed`) is skipped.

## When to Skip Tests

Skipping tests is useful in situations such as:

- **Focusing on specific functionality**: Temporarily ignore tests unrelated to what you’re actively working on.
- **Incremental development**: Skip tests for features that aren’t fully implemented yet.
- **Debugging test setups**: Skip problematic tests while diagnosing setup or environment issues.

Always remember to revisit and enable skipped tests (remove the `x`) once you’re ready to address them. Skipping tests should be a temporary measure, not a long-term solution.

### Key takeaway

Using `xdescribe`, `xtest`, or `xit` allows you to control which tests run during your development process. This flexibility can help you stay focused, but be mindful of re-enabling skipped tests to ensure all parts of your application are eventually covered by your test suite.
