Developing applications requires a strong effort for installing the right environment and tools.

Since I'm a lazy guy, I've created a tool that let you develop node.js applications and deploy them.
This tool is a simple buildout configuration (http://buildout.org).

Environment setup
-----------------

Enter to the buildout directory

$ cd node_mongo_buildout

Create a python virtualenv

$ virtualenv --no-site-packages -p python2.7 .

Bootstrap the buildout

$ bin/python bootstrap.py -v 2.1.0

Launch the buildout script: it will install node, the af gem script, gem, express.
The buildout script 

$ ./bin/buildout

Done!

Add an application
------------------

Create from scratch, for example with express

$ ./bin/express ..

Or configure the buildout cloning a git repo (TODO)

Application deploy @appfog
--------------------------

appfog.com

Login with:

$ ./bin/af login

Finally from within your source code directory:

$ ./bin/af update src/hello-node
