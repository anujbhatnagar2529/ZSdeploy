# ZSdeploy

Developer just needs to provide variable inside the file and commit the changes and Done !

It will automatically trigger the Jenkins build and deploy all the changes in the production/client environment.

In the below code snippet from the Jenkinsfile, please change value of ZSclientA.html to anyThingYouLike.html
and see the logic working...

----------------------------------------------------------------------------
					// User provided input to change the URL of deployed app
					sh '/var/www/html/accessURL.sh ZSclientA.html'
---------------------------------------------------------------------------

Hope it helps
