# Heroku Buildpack: wkhtmltopdf

This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for using [wkhtmltopdf](http://wkhtmltopdf.org/) in your application.

It is designed to be used with [heroku-buildpack-multi](https://github.com/ddollar/heroku-buildpack-multi) to combine it with the appropriate real buildpack for your app.

This is based on https://github.com/jayzes/heroku-buildpack-pngquant.

### Versions

The following wkhtmltopdf versions are available:

[Version 0.12.2.1 released on January 19, 2015](https://github.com/rafaelp/heroku-buildpack-wkhtmltopdf/tree/0.12.2.1)

[Version 0.12.1 released on June 26, 2014](https://github.com/rafaelp/heroku-buildpack-wkhtmltopdf/tree/0.12.1)

This branch works with version `0.12.2.1`

### Stack

This is designed to be used on [Cedar-14 Stack](https://devcenter.heroku.com/articles/cedar).

## Usage

Add a `.buildpacks` file to the root of your repo that contains this buildpack URL and your real buildpack URL:

    https://github.com/rafaelp/heroku-buildpack-wkhtmltopdf#0.12.2.1
    https://github.com/heroku/heroku-buildpack-ruby

Then create an application using the multi buildpack:

    $ heroku create --stack cedar-14 --buildpack https://github.com/ddollar/heroku-buildpack-multi

or configure an existing application:

    $ heroku config:set BUILDPACK_URL=https://github.com/ddollar/heroku-buildpack-multi

Deploy your applicatio.

    $ git push heroku master

Remember to clean your repository cache if you are updating the version of buildpack. To do that, run:

    $ heroku plugins:install https://github.com/heroku/heroku-repo.git
    $ heroku repo:purge_cache -a appname

You can verify that everything is properly installed by running the following command:

    $ heroku run "wkhtmltopdf -V"

The output should be:

    wkhtmltopdf 0.12.2.1 (with patched qt)

## Issues

If you have problems, please create a [Github Issue](https://github.com/rafaelp/heroku-buildpack-wkhtmltopdf/issues).

## Credits

heroku-buildpack-wkhtmltopdf was originally written by [Rafael Lima](http://rafael.adm.br).

Working at [Boleto Simples](https://boletosimples.com.br)

Github: [http://github.com/rafaelp](http://github.com/rafaelp)

Twitter: [http://twitter.com/rafaelp](http://twitter.com/rafaelp)

## License

heroku-buildpack-wkhtmltopdf is Copyright © 2014 Rafael Lima. It is free software, and may be redistributed under the terms specified in the [LICENSE](https://github.com/rafaelp/heroku-buildpack-wkhtmltopdf/blob/master/LICENSE) file.
