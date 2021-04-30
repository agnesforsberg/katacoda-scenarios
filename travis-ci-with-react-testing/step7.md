## What happens if you change the functionality of a method but not break the application? ##


Sometimes we rewrite methods or add new ones to apps without breaking the code. It is therefore very vital not to change the functionality of different already established features or functions. How can a team make sure that these mistakes are caught before they deploy it out to production.

Unit tests and tests are the solution to this problem. Here is an example you can try out where we actively change the funtionality of the plus button and we will see how Travis reacts to that.

In the forked repo, enter the file `src/App.js` and replace the number 1 in the plus COUNTER from line 14 to whatever number you want. Push your changes to Github.com

Now this is a tutorial and it might be quite obvious what will happen. However imagine you change 100 lines of codes - that might not be as easy to investigate.

In this case we know that one of our React tests (created in step 3) checks whether the plus button only increments by one each time. So how will travis react?

Well you will see the quite familiar Build failed error in the Travis CI dashboard, however if you look at the logs the results will be different...

<iframe src="https://drive.google.com/file/d/17nqU3AYBzpW-l6y6WC7ZkbAn0klRegsy/preview" width="640" height="280"></iframe>

First of all the build test will compile successfully as seen below, that is because the application itself has not been broken. 


<iframe src="https://drive.google.com/file/d/1UIWi84gr55e2YsZCwcm2rKQXEbUZOg7b/preview" width="640" height="180"></iframe>


However Travis will still fail the build and give a red X due to the fact that one of the tests failed as you can see below.

<iframe src="https://drive.google.com/file/d/1ueDjaZvxOPbjaheh6hC2EiWZZhVoqX4J/preview" width="640" height="180"></iframe>

This will show you that the code that you changed has affected the functionality of the application in a bad way and therefore you should not merge it in unless that mistake is fixed. This small blockade is so important for Continious integration and automation of DevOps projects and teams where the changes can be much bigger and have greater collisions.




