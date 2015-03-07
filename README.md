# Colonizers

A HTML5 multiplayer game, based on the popular board game ["Catan" (formerly "The Settlers of Catan")](http://en.wikipedia.org/wiki/The_Settlers_of_Catan) by Klaus Teuber.

Works across multiple devices (desktops, tablets, and mobile phones).

![Screenshot](http://i.imgur.com/j91XT2y.png)


## A work in progress!

Colonizers is very much a work in progress, with several critical gameplay
features still to be implemented. Breaking changes are to be expected, and the database schema may change.

Contributions (both issues and pull requests) are very welcome!


## Try it out on Heroku...

[![Deploy](https://www.herokucdn.com/deploy/button.png)](https://heroku.com/deploy)


## Running locally

Make sure you have [Node.js](https://github.com/joyent/node/wiki/Installation) and [MongoDB](http://www.mongodb.org/display/DOCS/Quickstart) installed.

```
git clone https://github.com/sibartlett/colonizers.git
cd colonizers
npm install
npm start
```

The app should now be running at [http://localhost:8080](http://localhost:8080)


## Setting up a development environment

The following script does the following:

* creates a directory named colonizers
* clones each component into a subdirectory
* uses ```npm link``` to symlink components into the NPM global store
* uses ```npm link``` to symlink dependencies from the NPM global store into components
* installs third-party dependencies using ```npm install```

```
mkdir colonizers
cd colonizers

git clone git@github.com:colonizers/colonizers-dev.git dev
cd dev
npm install
npm link
cd ..

git clone git@github.com:colonizers/colonizers-core.git core
cd core
npm install
npm link
cd ..

git clone git@github.com:colonizers/colonizers-client-tilesets.git tilesets
cd tilesets
npm install
npm link
cd ..

git clone git@github.com:colonizers/colonizers-client.git client
cd client
npm link colonizers-dev
npm link colonizers-core
npm install
npm link
cd ..

git clone git@github.com:colonizers/colonizers-server.git server
cd server
npm link colonizers-dev
npm link colonizers-core
npm install
npm link
cd ..

git clone git@github.com:colonizers/colonizers.git app
cd app
npm link colonizers-client
npm link colonizers-client-tilesets
npm link colonizers-server
npm install
```
