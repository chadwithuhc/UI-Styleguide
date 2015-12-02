# Developers Read Me

Instructions for getting this repo setup locally and committing changes.


## Setup

Clone down the repo locally:

`git clone https://github.com/bythepixel/css css-style-guide`

You will need to install Docpress globally with:

`npm install -g docpress`

Then, install the local npm modules with:

`npm install`


## Running Local Server

To run the server locally and live watch changes, use the command:

`docpress`


## Build and Deploy

Build the project by running the following command:

`npm run build`

Then, to deploy use:

`npm run deploy`

It will automatically commit changes to the `gh-pages` branch which is auto-pushed to the web.