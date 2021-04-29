It's time to write som tests to make sure our application is doing what it should! This is not a very complicated app, and you can probably tell it is working fairly well, but with a larger project tests are a great way of minimizing bugs!

## Getting started
There is already a test file provided when creating React apps with npx (which this one was). We will be using `testing-library@react` for our tests. Open `travis-react-tutorial/counter/src/App.test.js`{{open}} to see it!

## Writing tests
As you can see, the file is empty. Let's start by importing what we need:
<pre class="file" data-filename="travis-react-tutorial/counter/src/App.test.js" data-target="replace">
import { fireEvent, render, screen } from '@testing-library/react'
import App from './App'

#TODO-insertTest1

#TODO-insertTest2

#TODO-insertTest3
</pre>

The first import get's the necessary functions from the testing library - we'll go over these soon. And the of course we import our App, how else would we test it?

