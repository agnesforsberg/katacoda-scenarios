### What happens when you commit changes from now on ###

Finally it has become time to see the CI server in action. 🎉

As mentioned in the previous step it is important to ensure that the changes occur in the *time2Fork* branch. It is good practice to work in a different branch and the pull request the changes and merge. The reason for that is that whenever a pull request shows red that it does not get merged into the production environment minimizing bugs and errors. However for the purposes of this simple tutorial, we will conduct our changes directly to the default branch. 

In the forked repo, enter the file `src/App.js` and replace the word COUNTER from line 10 to whatever word you want. Push your changes to Github.com

 ⚠ **NOTE** For the purposes of this tutorial, dont worry about the commit messages and their contents

#### Testing phase ####

Travis is automatic as mentioned however it still has to test the whole application after each push and therefore it takes some time for the build to either pass or fail. However you can follow the progress of this process in the dashboard of travis CI under the column JOB LOG. During this Phase you should be able to see a yellow symbol in both Github and the Travis CI dashboard as seen in the images below.

*Travis CI dashboard:*
<iframe src="https://drive.google.com/file/d/1sPSk9ilbasOP23jwAPSLaCC_onEwWlgC/preview" width="600" height="280"></iframe>

*Github:*
<iframe src="https://drive.google.com/file/d/1C7ddbGWNIAehdWexFy4jYUtTCZCDUxE0/preview" width="640" height="180"></iframe>

⚠ **NOTE** The first build will always take the longest time as NPM in this case has to install the node_modules and build the project. This however is only done during the first pushed change after travis has been integrated to the project.


#### Sucessful build ####

Because you did not change anything too vital in the code, it should not have been broken and therefore the build is successful. If a build is successful  you should be able to see a green symbol in both Github and the Travis CI dashboard as seen in the images below.


*Travis CI dashboard:*
<iframe src="https://drive.google.com/file/d/135pNgX6vXqFvfVeCoDyb6ahHTn6gVMxv/preview" width="640" height="280"></iframe>

*Github:*
<iframe src="https://drive.google.com/file/d/1JOneLumXNjVcwwU0gSW2uKSsfwrrWOgC/preview" width="640" height="180"></iframe>


This shows that our change in our code has not broken the application and that it still functions perfectly.


#### Failed build

So we now it works if you dont break the code.. However what happens in the counter case. Lets break the code 👿

Enter the file `src/App.js` and replace the word *function* from line 4 to whatever word you want and then push your changes to Github. This will definately break the code and you can see in the Travis CI dashboard under the column JOB LOG what went wrong. When a build fails you should also be able to see a red symbol in both Github and the Travis CI dashboard as seen in the images below. 


*Travis CI dashboard:*
<iframe src="https://drive.google.com/file/d/1VTaxNnVdkgdTy9qElZ9CjiOaaOF3jWB3/preview" width="640" height="280"></iframe>

*Github:*
<iframe src="https://drive.google.com/file/d/14levq7-pjXBAvrWwBaF7RFpFIKuRToZj/preview" width="640" height="180"></iframe>


*The Job log showing what went wrong:*

<iframe src="https://drive.google.com/file/d/1LOutU156eTGPTNmr1fBw4IPmVVfbFKk2/preview" width="640" height="180"></iframe>


<p>
<p>

❗ __Fix the error immediately and push it before progressing to the next step!__ ❗


Now we have shown how the script `Node run build` affects the travis file and the importance of ensuring that , next we will see the importance of React tests where the app might not be broken but still works in the wrong way.



