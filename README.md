# Heroku buildpack: vendored makefile


This is a [Heroku buildpack](http://devcenter.heroku.com/articles/buildpacks) for running a single Makefile in the `heroku` directory of your project. It doesn’t do anything else, so to actually compile your app you should combine it with another buildpack (ex. python, node, etc.).

## Usage

    $ ls
    heroku
    .buildpacks

    $ ls heroku
	Makefile

    $ heroku create --buildpack https://github.com/tomaratyn/heroku-buildpack-vendored-makefile

    $ git push heroku master
    ...
    -----> Heroku receiving push
    -----> Fetching custom buildpack
    -----> Found a Makefile
    ...

The buildpack will detect that your app has a `Makefile` in the `heroku` directory. It will call `make` to execute the default target.

## About

Based on [Pete Peen’s](https://github.com/peterkeen) excellent [heroku-buildpack-vendorbinaries](https://github.com/peterkeen/heroku-buildpack-vendorbinaries).
