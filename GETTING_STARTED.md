## Running Locally for Development

1. ```git clone https://github.com/tamu-edu-students/TopMate-Clone.git```
2. ```cd topmate-clone```
3. Install Ruby and Rails
   1. [Ruby Intro](https://github.com/tamu-edu-students/hw-ruby-intro)
   2. [Ruby Docs](https://ruby-doc.org/)
4. Install/Start local Postgres db
   1. [Docker image](https://hub.docker.com/_/postgres)
   2. [MacOS](https://www.sqlshack.com/setting-up-a-postgresql-database-on-mac/)
   3. [GUI OSX/Linux/Windows](https://www.prisma.io/dataguide/postgresql/setting-up-a-local-postgresql-database)
5. Export environment variables
   1. ```export TOPMATE_DB_DEV_HOST=localhost```
   2. ```export TOPMATE_DB_DEV_PORT=5432```
   3. ```export TOPMATE_DB_DEV_USER=<your postgres username>```
   4. ```export TOPMATE_DB_DEV_PASS=<your postgres password> ```
6. Create/migrate db’s
   1. ```rake db:create```
   2. ```rake db:migrate```
   3. ```rake db:seed```
      1. optional but recommended, 95% of functionality requires a user's existence
7. Run tests
   1. ```rspec```
   2. ```rails cucumber```
8. Run server
   1. ```rails server```
9.  Start contributing

## Deploying to New Heroku App

1. ```git clone git@github.com:tamu-edu-students/TopMate-Clone.git```
2. ```cd topmate-clone```
3. Install Heroku cli
   1. [Instructions here](https://devcenter.heroku.com/articles/heroku-cli)
4. Log into heroku
   1. ```heroku login```
5. Create new heroku app
   1. ```heroku create <new name for app>```
6. Add production postgres DB to app
   1. ```heroku addons:create heroku-postgresql:mini```
7. Deploy repo to heroku
   1. ```git push heroku main```
   2. if you encounter errors, the heroku origin may not have been added to your repo, [resource here](https://stackoverflow.com/questions/18469737/git-push-heroku-master-error-repository-not-found)
8. Migrate DB 
   1. ```heroku run rake db:migrate```
9.  ```heroku open```
    1. if you ran `rake db:seed` you can login with a temp user using
        1.  Email: johndoe@gmail.com
        2.  Password: password
    2. Or visit John Doe's public page at the path `/public/JohnDoe`

This should spin up a production instance of the repo and open the app at the created url.
Remember, this app needs a user to be seeded to access the majority of the functionality.
