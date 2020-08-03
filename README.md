# linuxserver/laravel

This is a docker template based on the [linuxserver/nginx](https://docs.linuxserver.io/images/docker-nginx) image with some added scripts to work with Laravel applications.

## Getting started

To Start with, this container only serves a static page. here's what you need to do to get your Laravel site running:

Place your laravel site files in `conf/site`

Update `conf/etc/cont-init.d/50-laravel`. This script runs every time the container starts and will handle migrations and `.env` setup.

You will need to uncomment the relevant lines to generate app keys, and perform migrations.

If your app needs to use Laravel's queue system, you will also need to uncomment the command in `conf/etc/services.d/run` in order to start the queue worker.

Finally, you can build the image by running `docker build . -f Dockerfile`
