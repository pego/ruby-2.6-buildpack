# Custom Ruby Buildpack for Heroku

This custom buildpack allows you to use Ruby versions not officially supported by Heroku.

## How to use it

1. Add the buildpack to your Heroku application:
   ```bash
   heroku buildpacks:add https://github.com/tuo-username/my-ruby-buildpack.git
   ```

2. Specify the Ruby version in your `Gemfile`:
   ```ruby
   ruby '2.6.10'
   ```

3. Deploy:
   ```bash
   git push heroku main
   ```

## Buildpack Structure

- `bin/detect`: Determines if the app uses Ruby.
- `bin/compile`: Downloads and installs the specified Ruby version.
- `bin/release`: Defines execution processes for Heroku.

## Notes

Make sure your `Gemfile` and `Gemfile.lock` files are up to date.