<h1>
  <span class="headline">Test Driven Development with Jest</span>
  <span class="subhead">Setup</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to implement new functions that satisfy predefined test conditions, demonstrating the ability to apply TDD principles to write reliable and maintainable code.

## Practicing TDD

Now it’s time to practice putting TDD into action. We’ve got some test cases waiting for you, and your job is to write code that makes these tests pass. Don’t worry if it feels a bit backwards at first—this is part of the process. By the time you’re done, you’ll be more comfortable with TDD and how it helps ensure that every change you make is guided by a clear requirement.

To get started:

1. **Copy the starter code:**  
   Copy and paste the tests below into your `functions.test.js` file.

2. **Write functions to satisfy the tests:**  
   Open your `functions.js` file and define the functions exactly as they’re named in the provided tests. Each function should do just enough to pass the tests.

3. **Export the new functions:**  
   Make sure all your newly created functions are added to `module.exports` at the bottom of `functions.js`. This lets the test file know where to find them.

4. **Import you functions into the test file:**  
   At the top of your `functions.test.js` file, add the necessary imports to bring in your functions. If you forget this step, Jest won’t know how to access your code.

5. **Run the tests and iterate on your work:**  
   Copy the provided tests into your `functions.test.js` file. Notice how each test block is prefixed with an `x` in `xdescribe`. Remove the `x` to enable each set of tests, one at a time, and run `npm test` (or `npm run test`) to see if everything passes. If a test fails, adjust your code and run it again. Keep going until all tests are green!

## The starter code

Copy these tests into your `functions.test.js` file. Remember to remove the `x` before each `describe` block when you’re ready to tackle that set of tests.

```js
xdescribe('subtractTwoNumbers', () => {
  it('subtracts second number from first', () => {
    expect(subtractTwoNumbers(3, 1)).toBe(2);
    expect(subtractTwoNumbers(27, 7)).toBe(20);
    expect(subtractTwoNumbers(5.5, 3.5)).toBe(2);
  });

  it('returns an error message if incorrect data types are passed', () => {
    expect(subtractTwoNumbers(1, '1')).toBe(dataTypeError);
    expect(subtractTwoNumbers(11, {})).toBe(dataTypeError);
    expect(subtractTwoNumbers([], {})).toBe(dataTypeError);
  });
});

xdescribe('transformString', () => {
  it('should take a string and return it in uppercase', () => {
    expect(transformString('hello', 'uppercase')).toBe('HELLO');
    expect(transformString('lOuDeR pLeAsE', 'uppercase')).toBe('LOUDER PLEASE');
  });

  it('should take a string and return it in lowercase', () => {
    expect(transformString('GOODBYE', 'lowercase')).toBe('goodbye');
    expect(transformString('QuIeTeR pLeAsE', 'lowercase')).toBe(
      'quieter please'
    );
  });

  it('returns an error message if incorrect data types are passed', () => {
    expect(transformString(123, 'uppercase')).toBe(dataTypeError);
    expect(transformString([], 'uppercase')).toBe(dataTypeError);
  });
});

xdescribe('divisibleBy5', () => {
  it('should return true if the number is divisible by 5', () => {
    expect(divisibleBy5(15)).toBe(true);
    expect(divisibleBy5(45)).toBe(true);
    expect(divisibleBy5(5)).toBe(true);
  });

  it('should return false if the number is not divisible by 5', () => {
    expect(divisibleBy5(7)).toBe(false);
    expect(divisibleBy5(13)).toBe(false);
    expect(divisibleBy5(29)).toBe(false);
  });

  it('returns an error message if incorrect data types are passed', () => {
    expect(divisibleBy5('surprise!')).toBe(dataTypeError);
    expect(divisibleBy5({})).toBe(dataTypeError);
  });
});
```

By the end of this exercise, you’ll have firsthand experience with TDD’s benefits. You’ll be writing cleaner, more purposeful code, and you’ll have the tests to prove it works. Good luck, and have fun!
