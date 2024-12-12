<h1>
  <span class="headline">Test Driven Development with Jest</span>
  <span class="subhead">Getting Started with Jest</span>
</h1>

**Learning objective:** By the end of this lesson, students will be able to create a basic testing environment using Jest.

## Introducing the testing framework: Jest

[Jest](https://www.npmjs.com/package/jest) is a JavaScript testing library that helps ensure your code behaves as expected. Think of it as a tool that runs your functions and checks if their results match what you expect. If the results are correct, the test passes; if they’re not, the test fails. This helps you catch problems early, before they affect users.

In simpler terms, Jest allows you to say, "I expect this function to return X." If the function returns anything else, Jest will alert you, so you can quickly fix the issue in your code.

## Setting up a new project for testing

Let’s walk through the process of setting up a simple project to use Jest.

### 1. `cd` into the directory you created during setup

This folder will hold all the files you need for this exercise.

```bash
cd test-driven-development-with-jest
```

### 2. Initialize npm:

Jest is a package we’ll install using npm. From inside your `test-driven-development-with-jest` directory, run the following command:

```sh
npm init
```

Just press **Enter** through all the prompts—don’t worry about the details right now. You’ll end up with a `package.json` file that keeps track of your project’s dependencies and scripts.

### 3. Install Jest:

With npm set up, you can install Jest:

```sh
npm install jest
```

### 4. Configure your test scripts:

Now we need to tell npm how to run Jest. Open your `package.json` file and add the following scripts:

```json
"scripts": {
"test": "jest",
"test:watch": "jest --watch"
}
```

By adding these lines, you’re telling npm:

- **"test"**: Run Jest one time and show the results.
- **"test:watch"**: Run Jest in watch mode, which will re-run your tests every time you change a file. This can be really helpful when you’re in the middle of development and want immediate feedback.

Your entire `package.json` might now look like this:

```json
{
  "name": "test-driven-development-with-jest",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "scripts": {
    "test": "jest",
    "test:watch": "jest --watch"
  },
  "author": "",
  "license": "ISC",
  "devDependencies": {
    "jest": "^27.3.1"
  }
}
```

This setup is a starting point. As you write tests and code, you’ll run `npm test` to see if everything’s working smoothly.

At this stage, you’ve got Jest installed and ready to go. In the upcoming lessons, you’ll learn how to actually write tests, run them, and use TDD to guide how you build out features. The idea is that by writing tests first, you’ll have a clear target for what your code should do—and you’ll know immediately when something isn’t quite right.
