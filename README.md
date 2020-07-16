# Deploying a Spring Boot app on Heroku using Git and Heroku CLI

## Steps To Perform

Before you start deployment you need to have a Heroku account. Once you’re registered with Heroku, follow the steps below to deploy the Spring Boot app.

### 1. Download and install Heroku CLI

Heroku CLI is a command line application which allow you to create, deploy and manage Heroku apps.

### 2. Get Logged in to your Heroku account

Enter the following command to login to Heroku using Heroku CLI


Run the following commands in two separate terminals to create a blissful development experience where your browser
auto-refreshes when files change on your hard drive.

```
heroku login
```

A message will be prompted to enter your Heroku account’s credentials.

```
Enter your Heroku credentials:
Email: vjoshi@gmail.com
Password: **************
Logged in as vjoshi@gmail.com
```

You’re logged in to Heroku.

### 3. Set up Git and generate a Heroku app

Execute the following commands from the root directory of the project to create a local Git repository for the project -

```
git init
git add .
git commit -m "initial commit"
```

Now, create a new heroku app using heroku command

```
heroku create
```

### 3. Voilà That's it!!

you can deploy the app by pushing the code to the repository which you just created.

```
git push heroku master
```

Heroku detects that the app and triggers the build accordingly.



##This way is not ideal in follwing cases,

Your project is closed source and you don’t want to push the source code to Heroku.
Your project uses some dependencies that are internally developed for specific usage on premise only.
In this case the source code won’t compile at Heroku because it won’t be able to download the internal dependencies.


Meanwhile you can also deploy executable jar/war of your project on Heroku by executing follownig commands with addition of above,

```
heroku plugins:install heroku-cli-deploy

heroku deploy:jar target/heroku-demo-0.0.1-SNAPSHOT.jar --app <APP-NAME>

```