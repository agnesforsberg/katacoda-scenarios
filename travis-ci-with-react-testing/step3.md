It's time to write som tests to make sure our application is doing what it should! This is not a very complicated app, and you can probably tell it is working fairly well, but with a larger project tests are a great way of minimizing bugs!

## Getting started
We will be using Jest for our testing. Jest is a testing framework for Javascript that is common for testing in React. We need to install it to use it.
First run `^C`{{execute ctrl-seq}} to stop our app from running, and then run ```npm install --save-dev jest```{{execute}} to install Jest. 

Then, in our `package.json`{{open}} file, find: 
```
{"scripts": {
        ...,
        "test" : "react-scripts test",
        ...
}}
```
and change "react-scripts test" to "jest", so that it says `"test": "jest"`.
