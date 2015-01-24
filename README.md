# Heroku buildpack: Vert.x

This is a buildpack for [Vert.x](http://vertx.io/) apps, used to deploy vert.x apps in IBM Bluemix. An example app can be found [here](https://github.com/mthenw/vertx-sample).

Currently it uses following versions:

* JDK **1.7**
* Vert.x **2.1.4**

You can vary those versions by adjusting the OPENJDK7_URL and VERTX_URL constants in the bin/compile file

## Usage

This buildpack assumes that there are at least two files in repository:

* ```mod.json``` - used to determine if this is vert.x project
* ```server.js``` - by default file that will be launched (of course this can be overrided by Procfile)

Example usage:

    $ ls
    mod.json server.js

    $ heroku create --stack cedar --buildpack https://github.com/mthenw/heroku-buildpack-vertx.git

    $ git push heroku master

    -----> Fetching custom git buildpack... done
    -----> Vert.x app detected

    -----> Installing OpenJDK7u2..... done
    -----> Installing Vert.x..... done

    -----> Launching... done

This buildpack is based on [tomaslin/heroku-buildpack-vertx-jdk7](https://github.com/tomaslin/heroku-buildpack-vertx-jdk7).

## License

MIT
