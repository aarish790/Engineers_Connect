# Engineers_Connect
 A MERN Stack Web app in which you can create a student/engineer portfolio, share posts and can get help from other students/engineers.
 You can also add comments and can like and unlike them as well.
 Bcrypt with json web token is used for authentication (SignIn/SignUp).
 
 It is a Social Network for Engineers.
 
 Check out app at : https://sleepy-dusk-08610.herokuapp.com/
 
# Quick Start 🚀
Add a default.json file in config folder with the following
```
{
  "mongoURI": "<your_mongoDB_Atlas_uri_with_credentials>",
  "jwtSecret": "secret",
  "githubToken": "<yoursecrectaccesstoken>"
}
```
# Install server dependencies
```
npm install
```
# Install client dependencies
```
cd client
npm install
```
# Run both Express & React from root
```
npm run dev
```
# Build for production
```
cd client
npm run build
```
# Test production before deploy
After running a build in the client 👆, cd into the root of the project.
And run...

```
NODE_ENV=production node server.js
```
Check in browser on http://localhost:5000/

# Deploy to Heroku
If you followed the sensible advice above and included ```config/default.json``` and ```config/production.json``` in your .gitignore file, then pushing to Heroku will omit your config files from the push.
However, Heroku needs these files for a successful build.
So how to get them to Heroku without commiting them to GitHub?

What I suggest you do is create a local only branch, lets call it production.

```
git checkout -b production
```
We can use this branch to deploy from, with our config files.

Add the config file...

```
git add -f config/production.json
```
This will track the file in git on this branch only. 
#### DON'T PUSH THE PRODUCTION BRANCH TO GITHUB

Commit...

```
git commit -m 'ready to deploy'
```
Create your Heroku project

```
heroku create
```
And push the local production branch to the remote heroku master branch.

```
git push heroku production:master
```
Now Heroku will have the config it needs to build the project.

#### Don't forget to make sure your production database is not whitelisted in MongoDB Atlas, otherwise the 
#### database connection will fail and your app will crash.

After deployment you can delete the production branch if you like.
```
git checkout master
git branch -D production
```
Or you can leave it to merge and push updates from another branch.
Make any changes you need on your master branch and merge those into your production branch.
```
git checkout production
git merge master
```
Once merged you can push to heroku as above and your site will rebuild and be updated.





MIT License

Copyright (c) 2020 MD Aarish Siddiqui

Permission is hereby granted, free of charge, to any person obtaining a copy
of this software and associated documentation files (the "Software"), to deal
in the Software without restriction, including without limitation the rights
to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
copies of the Software, and to permit persons to whom the Software is
furnished to do so, subject to the following conditions:

The above copyright notice and this permission notice shall be included in all
copies or substantial portions of the Software.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
SOFTWARE.
