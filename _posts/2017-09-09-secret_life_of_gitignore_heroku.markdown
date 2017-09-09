---
layout: post
title:  "Secret life of (.gitignore/heroku)!"
date:   2017-09-09 19:56:13 +0000
---


Its not new to get stuck with a problem when coding, One such problem I faced this week was with the use of .gitignore, and having hard time to deploy my app on heroku. So decided to break done the problem and write a blog describing it.

![](https://media.giphy.com/media/3ohhwzvzIe3IM8JXHi/giphy.gif)

**So first thing, what was the problem ?** The React app I made required the use of Youtube api, The problem is not the api but hidding the key before pushing into github. 
Step 1/ I took to hide my key was to make **config.js** file make an Object which store the key

![](https://i.imgur.com/Y9Hcv8u.png)

Step2/ import the config file to the file where it require the use of API key.

![](https://imgur.com/SUX1KUo.png)

The end result was app was running perfectly fine. now the time came to push them all in github, so to hide the config.js file which hold so called confidential detail I listed it inside .gitignore file and pushed it to my github repository. Story ended and every thing was perfect .

**Problem Phase**
Deploying in Heroku:
If you push the code in heroku with hidden important file, your app will not run perfectly So whats the solution to solve this and yet remain hidden:

**Step 1** Create a separate branch for heroku that contains your target folder, say `herokuInfo`

`git checkout -b herokuInfo`

**Step 2** Modify the .gitignore file by removing config.js file, then

```

git add .
git commit -m "your commit message"

```
**Step 3** push the branch with config changes to heroku

```

git push heroku herokuInfo:master

```

So these are the remedies taken inorder to fix the issue, creating a branch in local systems git and pushing that version on heroku but not pushing into github repository , which secures the data and yet get deployed on heroku.

Hope the solution was helpful.



