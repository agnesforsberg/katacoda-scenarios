It's time to write som tests to make sure our application is doing what it should! This is not a very complicated app, and you can probably tell it is working fairly well, but with a larger project tests are a great way of minimizing bugs!

## Getting started
There is already a test file provided when creating React apps with npx (which this one was). We will be using `testing-library@react` for our tests. Open `/travis-react-tutorial/counter/src/App.test.js`{{open}} to see it!

## Writing tests
As you can see, the file is empty. Let's start by importing what we need:
<pre class="file" data-filename="/root/travis-react-tutorial/counter/src/App.test.js" data-target="replace">
import { fireEvent, render, screen } from '@testing-library/react'
import App from './App'

#TODO-insertTest1

#TODO-insertTest2

#TODO-insertTest3
</pre>

The first import get's the necessary functions from the testing library - we'll go over these soon. And the of course we then import our App, how else would we test it?

**Test 1**
Let's start with something basic, let's make sure our buttons are rendered on the page!
<pre class="file" data-filename="/root/travis-react-tutorial/counter/src/App.test.js" data-target="insert"  data-marker="#TODO-insertTest1">
test('test 2 buttons render', () => {
  render(<App />)
  const buttons = screen.getAllByRole('button')
  expect(buttons).toHaveLength(2)
})
</pre>

What is going on here?
- test() defines a test
- the first parameter, `'test 2 buttons render'` is a description
- the second parameter is the function that defines the test
- `render(<App/>)` renders the App in the testing environment
- `screen.getAllByRole('button')` returns an array of all buttons on the page
- `expect(buttons).toHaveLength(2)` checks if there are exactly 2 buttons

`expect()` is how we assert tests in React.

Run `npm run test`{{execute}} to check if the test succeeds!
