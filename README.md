AddBuildPackToBluemix
=====================

description to add your own buildpack to Bluemix

see Bluemix.net

if you want to add your own Buildpack, you can use a Cloud Foundry-compatible buildpack.

The buildpacks allready in Bluemix are the following:

run the cf buildpacks command:

    $ cf buildpacks 
    
    Getting buildpacks...       
    buildpack     position enabled locked filename 
    ... 
    java_buildpack    7     true    false buildpack_java_v2.0.2.zip 
    ruby_buildpack    8     true    false buildpack_ruby_v46-245-g2fc4ad8.zip 
    nodejs_buildpack  9     true    false buildpack_nodejs_v8-177-g2b0a5cf.zip

If you want to use buildpack to overwrite  IBM created buildpack, you must specifybuildpack by using 
-b option 
with  cf push command. 
For example, you can use  buildpack for Java™ web applications:

$ cf push app_name -b java_buildpack

or for node.js

$ cf push app_name -b nodejs_buildpack

or for ruby (external buildpack):

$ cf push app_name -b https://github.com/cloudfoundry/heroku-buildpack-ruby

Do this to deploy your application with  custom buildpack:

For organization_name and space_name, you can use the defaults. default organization = user name, default space = dev.

    $ cf login -a api.ng.bluemix.net -u user_name -p password -o organization_name -s space_name

  then issue command with  -b option to deploy  app with  own buildpack:

    $ cf push app_name -b buildpack_URL

For example, with PHP 

$ cf push app_name -b https://github.com/dmikusa-pivotal/cf-php-build-pack


