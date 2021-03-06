Seer-UI
============
[中文版](README_zh.md)

This is a light wallet that connects to a Seer API provided by the *witness_node* executable.


It *stores all keys locally* in the browser, *never exposing your keys to anyone* as it signs transactions locally before transmitting them to the API server which then broadcasts them to the blockchain network. The wallet is encrypted with a password of your choosing and encrypted in a browser database.

## Getting started

Seer-UI depends node Node.js, and version 6+ is required.

On Ubuntu and OSX, the easiest way to install Node is to use the [Node Version Manager](https://github.com/creationix/nvm).

To install NVM for Linux/OSX, simply copy paste the following in a terminal:

```
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.30.2/install.sh | bash
nvm install v6
nvm use v6
```

Once you have Node installed, you can clone the repo:

```
git clone https://github.com/seer-project/seer-ui.git
cd seer-ui
```

Before launching the GUI you will need to install the npm packages:

```
npm install
```

## Running the dev server

The dev server uses Express in combination with Webpack.

Once all the packages have been installed you can start the development server by running:

```
npm start
```

Once the compilation is done the GUI will be available in your browser at: `localhost:9080` or `127.0.0.1:9080`. Hot Reloading is enabled so the browser will live update as you edit the source files.


## Production
If you'd like to host your own wallet somewhere, you should create a production build and host it using NGINX or Apache. In order to create a prod bundle, simply run the following command:

```
npm run build
```
This will create a bundle in the /dist folder that can be hosted with the web server of your choice.


### Installable wallets
We use Electron to provide installable wallets, available for Windows, OSX and Linux Debian platforms such as Ubuntu. First, make sure your local python version is 2.7.x, as a dependency requires this.

On Linux you will need to install the following packages to handle icon generation:

`sudo apt-get install --no-install-recommends -y icnsutils graphicsmagick xz-utils`

For building, each architecture has it's own script that you can use to build your native binary:

__Linux__
`npm run package-deb`  
__Windows__
`npm run package-win`  
__Mac__
`npm run package-mac`  

This will compile the UI with some special modifications for use with Electron, generate installable binaries with Electron and copy the result to the root `build/binaries` folder.


### Docker

Clone this repository, run `docker-compose up` and visit localhost:9080 

## Development process

- Milestones are numbered YYMMDD and refer to the **anticipated release date**.
- Bugs are always worked before enhancements
- Developers should work each issue according to a numbered branch corresponding to the issue `git checkout -b 123`
- We pay **bounties** for issues that have been estimated. An estimated issue is prefixed with a number in brackets like this: `[2] An nasty bug`. In this example, the bug is valued at two hours ($125 per hour). If you fix this issue according to these guidelines and your PR is accepted, this will earn you $250 bitUSD. You must have a Seer wallet and a Seer account to receive payment.
- If an issue is already claimed (assigned), do not attempt to claim it. Issues claimed by outside developers will indicate an assignment to wmbutler, but will mention the developer's github account in this the comments.
- To claim an issue, simply leave a comment with your request to claim.
- Do not claim an issue if you will be unable to complete it by the date indicated on the Milestone name. Milestone 170901 will be pushed on September 1, 2017.

## Coding style guideline

Our style guideline is based on 'Airbnb JavaScript Style Guide' (https://github.com/airbnb/javascript), with few exceptions:

- Strings are double quoted
- Additional trailing comma (in arrays and objects declaration) is optional
- 4 spaces tabs
- Spaces inside curly braces are optional

We strongly encourage to use _eslint_ to make sure the code adhere to our style guidelines.
