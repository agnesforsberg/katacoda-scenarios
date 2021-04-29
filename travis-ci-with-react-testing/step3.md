It's time to write som tests to make sure our application is doing what it should! This is not a very complicated app, and you can probably tell it is working fairly well, but with a larger project tests are a great way of minimizing bugs!

## Getting started
There is already a test file provided when creating React apps with npx (which this one was). We will be using `testing-library@react` for our tests. Open `/travis-react-tutorial/src/App.test.js`{{open}} to see it!

## Writing tests
As you can see, the file is empty. Let's start by importing what we need:
<pre class="file" data-filename="/root/travis-react-tutorial/src/App.test.js" data-target="replace">
import { fireEvent, render, screen } from '@testing-library/react'
import App from './App'

#TODO-insertTest1

#TODO-insertTest2

#TODO-insertTest3
</pre>

The first import get's the necessary functions from the testing library - we'll go over these soon. And the of course we then import our App, how else would we test it?

**Test 1**
Let's start with something basic, let's make sure our buttons are rendered on the page!
<pre class="file" data-filename="/root/travis-react-tutorial/src/App.test.js" data-target="insert"  data-marker="#TODO-insertTest1">
test('test 2 buttons render', () => {
  render(&ltApp />)
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

**Test 2 and 3**
Ok, so we have the buttons, but let's make sure that they work!

<pre class="file" data-filename="/root/travis-react-tutorial/src/App.test.js" data-target="insert"  data-marker="#TODO-insertTest2">
test('test number plus 1', () => {
    render(&ltApp/>)
    const plusButton = screen.getByRole('button', {name: '+'})
    const number = screen.getByText('1')
    fireEvent(plusButton, new MouseEvent('click', {
        bubbles: true,
        cancelable: true,
      }))
    expect(number.textContent).toBe('2')
})
</pre>

<pre class="file" data-filename="/root/travis-react-tutorial/src/App.test.js" data-target="insert"  data-marker="#TODO-insertTest3">
test('test number minus 1', () => {
    render(&ltApp/>)
    const minusButton = screen.getByRole('button', {name: '-'})
    const number = screen.getByText('1')
    fireEvent(minusButton, new MouseEvent('click', {
        bubbles: true,
        cancelable: true,
      }))
    expect(number.textContent).toBe('0')
})
</pre>

These tests are similar, but test the different buttons. We have a few new functions, let's go over them!

- `screen.getByRole('button', {name: '+'})` - this function can take one (which we saw in Test 1) or 2 arguments. The second argument specifies what name the node should have, in this case '+'.
- `screen.getByText(string) - this function returns the first node on the page with the text content supplied.
- fireEvent(node, event) - this function mimics an event on the page. In this case we supply it with our buttons and mimic a mouse click with `MouseEvent`
- `expect(number.textContent).toBe('2')` - This time we look at the number node again and make sure it has increased or decreased by one.

## Test the tests
Now we have some tests, let's see if they pass! Run `npm run test`{{execute}}
Woo, the tests pass! Press q in the terminal to quit, but don't do it yet!

⚠ **NOTE** If your tests don't pass, make sure you haven't changed anything in App.js and that you've copied the tests exactly as written here!

## Break the tests
This might not make any sense, but let's see if we can get a test to fail - just for fun!

Open `/travis-react-tutorial/src/App.js`{{open}} and change it so that the plus button adds 2 instead of 1 when clicked.

Since we didn't quit the testing before they should run again automatically. What happens?

You're told what went wrong - what it expected and what it got. When writing tests, and the tests fail, this is a great way to debug what's going wrong with your code.

🚨**Don't forget** to get your code back to working! Then press `q` to get back to your terminal.