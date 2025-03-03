# Ruby 2.6.10 Buildpack for Heroku

This custom buildpack compiles Ruby 2.6.10 with OpenSSL 1.1.1 from source on Heroku during deployment.

## Features

- Compiles OpenSSL 1.1.1w from source
- Compiles Ruby 2.6.10 from source
- Caches downloaded source files to speed up subsequent builds
- Compatible with heroku-24 stack
- Automatically installs Bundler
- Sets up proper environment variables for Ruby and OpenSSL

## How to Use

1. Add this buildpack to your Heroku application:
   ```bash
   heroku buildpacks:set https://github.com/your-username/ruby-2.6-buildpack.git -a your-app-name
   ```

2. Specify Ruby 2.6.10 in your Gemfile:
   ```ruby
   ruby '2.6.10'
   ```

3. Deploy your application:
   ```bash
   git push heroku main
   ```

## Notes

- First build will take longer since it compiles both OpenSSL and Ruby from source
- Subsequent builds will be faster as source files are cached
- The build process requires sufficient memory and CPU, so it may not work on free tier dynos
- The compiled Ruby is configured to use the compiled OpenSSL 1.1.1w version

## Troubleshooting

If you encounter issues:

1. Check the build logs for compilation errors
2. Make sure your app has enough memory for the compilation process
3. Try clearing the build cache: `heroku builds:cache:purge -a your-app-name`

## License

MIT License