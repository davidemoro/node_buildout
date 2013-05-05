Developing applications requires a strong effort for installing the right environment and tools.

This is a tool that allows you to automatically build an environment ready to use that let you develop node.js applications and deploy them.
See http://buildout.org in order to know what are buildout environments.

Environment setup
-----------------

Enter to the buildout directory

    $ cd node_mongo_buildout

Create a python virtualenv

    $ virtualenv --no-site-packages .

Bootstrap the buildout

    $ bin/python bootstrap.py

Launch the buildout script: it will install node, the af gem script, gem, express.

The buildout script 

    $ ./bin/buildout

Done!

Now you have a local installation of node, express and appfog tools for deploy your application online.
If your application needs a storage solution, you can tell your buildout to add a local mongo db.

Add an application
------------------

You can configure the buildout cloning a for example 'myapp' git repo. Configure the sources section of buildout.cfg
and re-runa the buildout script.

Alternatively create a new one from scratch with express:

    $ ./bin/express express --sessions --css stylus --ejs myapp

See more details on http://expressjs.com/guide.html#executable


Install the dependencies of your app
------------------------------------

Install the dependencies

    $ ./bin/npm install src/myapp


Run your application
--------------------

Command:

    $ ./bin/node src/myapp app


Deploy your application at @appfog
----------------------------------

Create an account at http://appfog.com.

Login with:

    $ ./bin/af login

Finally from within your source code directory:

    $ ./bin/af update src/myapp
