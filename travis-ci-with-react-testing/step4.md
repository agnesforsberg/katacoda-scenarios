### How travis works 

As mentioned in Step 1, making changes can be risky in large projects and minor changes in code can really break how the application functions works. Instead of manually checking for these changes, we can use the Continous integration tool Travis CI.

Travis is a Continuous Integration server that integrates with Github to show the user whether their commits have broken the build in any way.

This automation which is an integral part of continuous integration can be configured in many different ways such as adding unit tests, load tests etc. However in this tutorial we will only focus on the simple React tests that were conducted in step 3.



### How to configure travis to your repo

For a travis integration to work, your Github repo has to have a `/travis-react-tutorial/.travis.yml`{{open}} file which contains the configuration information  and it must be in the root folder of your Github repo.

💡 Tip: click on the file name above to create the file in the editor automatically!

#### Travis structure

A simple travis configuration file is divided into 3 parts: 
- language
- version 
- scripts

The language tells the CI server what language the code utilizes in its builds. The language used for React environments is Node_js:

<pre class="file" data-filename=".travis.yml" data-target="append">language: node_js
</pre>


The version can be specified however as that is not the focus of this tutorial we will use a stable version of Node_js.



<pre class="file" data-filename=".travis.yml" data-target="append">node_js: 
  - "stable"
</pre>

Finally the Script part, which might be the most diverse part of the configuration file. It tells Travis what commands should be run when committing changes to the project.

<pre class="file" data-filename=".travis.yml" data-target="append">script:
  - npm run build
  - npm run test
</pre>

the final version of the Travis configuration file should look like this:

```
language: node_js
node_js:
  - "stable"
script:
  - npm run build
  - npm run test

```
⚠ **NOTE** This should be based on what build and test commands are specified in the `package.json`.


If you want to add more commands that travis can check just append them to the bottom part (eg. npm start etc.)


## How Travis tests occur 

The scripts: `npm run build` and `npm run test`  that were added to the configuration file will now run each time a change is commited to Github. For the Travis CI server to approve the change both the build has to be sucessfull and the React tests we added in step 3. This is to ensure that the code change does not affect the product itself or any of the functionalities of the product.

As mentioned earlier, other types of tests can be added to check for performance issues and scaling issues.


Now you have a `.travis.yml` file that contains the configuration information needed for the Travis CI server to work. The next step will show you how to integrate Travis with the Github repo.