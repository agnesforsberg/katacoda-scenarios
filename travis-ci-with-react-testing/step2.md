## Before you begin

The code you will need to complete this tutorial is provided in a Github repo that you will soon clone into Katacoda. We will not provide you with instructions to run the tutorial locally, **however** you can choose to do so if you already have som additional knowledge. In Step **TODO** you will need to fork the repo and perform the last steps locally, since you need push access to the repo. At that step we will provide you with a repo that has Step **TODO** already included.

### Set up

Clone the repo by running the following command: 

`git clone https://github.com/agnesforsberg/travis-react-tutorial.git`{{execute}}

Navigate into the project folder `cd travis-react-tutorial/counter`{{execute}}

and install the dependancies `npm install`{{execute}} This might take a little while, you can read ahead while you wait but don't go to the next step yet!


**NOTE** `npm install` will install all the needed dependancies for a React app to work, and put them in the folder *node_modules*. You don't need to know the specifics of the folder, and it is a part of our *.gitignore* file, which tells Github not to upload that folder when you run `git push`. This is because there are a very large number of files in *node_modules*, and we can simply install them each time we clone this repository.

### Getting to know the application
