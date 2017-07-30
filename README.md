# gtprojects

<h2>Compatibility<h2>
<p>
This application was written on a MacBook Pro (Retina, 13-inch) with macOS Sierra Version 10.12.5 (16F73).
I used ionic 1.7.16 for the development. 
Therefore it is possible it might not be compatible with newer versions of the ionic platform.
<p>
<hr>
<h2>i18n</h2>
<p>
For this project I used the angular-translate module (https://github.com/angular-translate/angular-translate)
In order to make it work I added a few bower components to this project over the terminal:
</p>
<code>
    bower install angular-translate
    bower install angular-translate-storage-cookie
    bower install angular-translate-loader-static-files
    bower install angular-translate-storage-local
</code>
<p>
Since I was getting an error, that there is a problem with angular-cookies I looked up a newer implementation of
this component. Currently the version of angular-cookies.min.js is 1.6.1 which eventually worked.
</p>

<hr>

<h2>Gulp Task</h2>
<p>
For the gulp task to work I had to install gulp first via npm and a few other gulp modules with the following 
commands in the terminal:
</p>
<code>
    npm install gulp
    npm install gulp-sass --save-dev
    npm install gulp-clean-css --save-dev
    npm install gulp-rename --save-dev
</code>    
<p>
I added the new gulp task at the end of gulpfile.js (in the root directory). This particular gulp task will be 
executed every time the application is launched because I linked it inside the ionic.project file (in the root directory):
</p>
<code>
    {
      "name": "testelshan",
      "app_id": "",
      "gulpStartupTasks": [
        "copyi18n"
      ]
    }
</code>

<p>
In the root folder there is a file inside i18n/es.json which is automatically being copied by the gulp task into 
the folder www/assets/i18n/ folder.
</p>
      
<hr>

<h2>Application launching</h2>
<p>
For starting the application all you need to is either go into the root directory over terminal and run the command:
</p>
<code>
  ionic serve
</code>
<p>
For starting the application in the iOS simulator go into the root directory over terminal and run the command:
</p>
<code>
  ionic emulate ios
</code> 
<p>
It is possible to open the Xcode project from testelshan/platforms/ios/testelshan.xcodeproj and run it from directly from 
Xcode.
</p>

<p>
The version Xcode I used is 8.3.3 (8E3004b) and I tested on an iPhone 6 and an iPhone 5 simulator.
</p>

<h2>UI design & use cases</h2>
<h3>First Screen:</h3>
<p>
    - After launching the app in the header bar on should shee 2 blue buttons for logging in and registering.
    - Clicking the Login button changes opens a modal view where one can type in an E-mail address and a password
      which get validated instantly.
    - The register button doesn't have any functionality since it was not specified.
    - In the middle of the first screen is a dropdown box for changing the UI language
</p>

<h3>Second Screen:</h3>
<p>
    - If the E-mail address and the password are valid the Send button is enabled and clicking on it will
      navigate to the List with JSON messages retrieved via AJAX
    - The messages are shown in a list with a title and a message body of the downloaded "posts"
</p>




    
    
    
