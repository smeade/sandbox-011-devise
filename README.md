## Readme

An application to experiment with the [Devise gem](https://github.com/plataformatec/devise) for authentication.

"Devise is a flexible authentication solution for Rails based on Warden"

Demo Heroku app is [here](http://sandbox-011-devise.herokuapp.com/).

## Notes
1. Heroku default_url_options

Devise uses the default url options in your environments files for composing relative links in confirmation and password recovery emails. For Heroku, configure and use a MAIL_HOST environment variable.

From the command line:

        heroku config:add MAIL_HOST=[YOUR APP URL]

In `production.rb`:

        config.action_mailer.default_url_options = { host: ENV['MAIL_HOST'] }

2. Review `config\initializers\devise.rb` for a variety of configuration options. As with all initializers, restart after modifying.

For example:

        config.password_length = 4..128

3. Review `devise.em.yml` (or locale file of your choice) for configurable messaging.

4. Read about required [test helpers](https://github.com/plataformatec/devise#test-helpers).

## Getting Started with this codebase

1. Install gems:

        bundle install

2. Create the database:

        rake db:create

4. Migrate the database:

        rake db:migrate

5. Start the web server:

        rails server

5. Using a browser, go to [http://localhost:3000](http://localhost:3000)

## Running the test suite

        rake

## Deploying to Heroku

1. Install the [Heroku toolbelt](https://devcenter.heroku.com/articles/getting-started-with-rails4#local-workstation-setup) on local workstation (if not already installed).

2. Create the [Heroku app](https://devcenter.heroku.com/articles/getting-started-with-rails4#deploy-your-application-to-heroku) (if not already created).

        heroku apps:create

3. [Deploy](https://devcenter.heroku.com/articles/git#deploying-code)

        git push heroku master

4. Run migrations

        heroku run rake db:migrate

5. Visit the deployed app

        heroku open

