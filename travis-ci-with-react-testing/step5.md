⚠ **NOTE** From this point on in the tutorial you will have to use a Github account


It's time to leave the safety of our Katacoda terminal. The last few steps have to be performed on Github. So go to [https://github.com/agnesforsberg/travis-react-tutorial](https://github.com/agnesforsberg/travis-react-tutorial) and fork the repo to your own profile.


⚠ **NOTE** You will be working in the branch *time2Fork*, where all of the steps you have already performed are prepared for you, so you do not have to do them again! Also dont forget to run `npm install` in the repo to get the node_modules directory as it is not on the Github repo if you want to test the code locally.

The first step is to ensure that you have decided what default branch the production code will be on. In most cases that is in the *Main* branch however for this tutorial we want you to change it to the *time2Fork* branch. This can be done in the fork repos Settings -> Branch and switch it from *Main* to *time2Fork* there. 

💡 Tip: It should look something like this image.  

<iframe src="https://drive.google.com/file/d/1BS7WPKchnht9xdq-pkLYfU7o3pOYgWIw/preview" width="640" height="480"></iframe>


Now it is time to finally integrate travis to the github repo

###  Authorize travis to Github


#### Steps: ####

1. Go to [https://travis-ci.com/](https://travis-ci.com/) and sign in or sign up using your github account.


    <iframe src="https://drive.google.com/file/d/1CdlzKcS_-fU41h45Y5Pza4NerkVFyXLd/preview" width="640" height="480"></iframe>


    ⚠ **NOTE** First time users will be prompted to authorize travis, this will not give travis access to the repo, you must carry on with the Steps.

    <iframe src="https://drive.google.com/file/d/1sv2kSAbJ5O6DZ2csTiytgGynJj4vOE9g/preview" width="640" height="480"></iframe>

2. Once in travis, click on your profile picture on the top right corner and click on settings. Once in Settings click on the green button that says *Activate* under **Github Apps integration** .



    <iframe src="https://drive.google.com/file/d/1QiO5dGIlLmQVPIiZA-Eptyl0Ztm7pCNS/preview" width="640" height="480"></iframe>




    Here you will be promted to either add all your github repos or a selected few. For the purposes of this tutorial you only need to give access for the forked repo you are working on. Then you approve and install it.


    <iframe src="https://drive.google.com/file/d/1k_hAsKi2HNKpOkQZez0iszXDO-MKoOIB/preview" width="640" height="480"></iframe>



3. Now you should be connected and any changes to the *time2Fork* branch will be tested and can either pass or fail. This can be seen both on github and on the Travis-CI dashboard. But more on that in the next step.
