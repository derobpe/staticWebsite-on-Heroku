# Heroku supported buildpacks
Listed on the Heroku reference page, the supported buildpacks offered are: Ruby, Node.js, Clojure, Python, Java, Gradle, Grails, Scala, Play, PHP, Go. These buildpacks are searched within the deployed repo based on the specified language used. However, the buildpacks are not offered for the typical HTML, CSS, Javascript languages. This explains the error you received: “no default language could be detected for this app”.

## Solution --> PHP
A small little trick to get Heroku to recognize the files of your static website is to trick it into being a PHP app. Yup, PHP.

## Steps
1. Head to the root directory of your project that contains index.html (the main HTML page).
2. In this directory, run ``` touch composer.json ``` to create a file: composer.json.
3. Within the file, add the following line: ```{}```
4. In the same directory, run ```touch index.php``` to create a file: index.php.
5. Within the file, add the following line: ```<?php include_once("index.html"); ?>```
6. Now, commit and push these two new files to your repository. You can also use the Heroku command ```git push heroku master```. Wait for the automatic deployment to work its magic.

Submarine with CSS
------------------
Result: 

Trying to replicate a [Pen](https://codepen.io/ajerez/pen/EaEEOW) by [Alberto Jerez](https://codepen.io/ajerez) on [CodePen](https://codepen.io).

[License](https://codepen.io/ajerez/pen/EaEEOW/license).