# simple-nodejs-app

Simple-nodejs-app is a simple web application created using [Node.js](https://github.com/nodejs/node). It uses [MediaWiki - Wikipedia's Search API](https://www.mediawiki.org/wiki/API:Opensearch) to search for anything entered by the user and parses the result in a JSON format. The infobox of the Wikipedia page is parsed using [wiki-infobox-parser](https://github.com/0x333333/wiki-infobox-parser).

## Download and Installation

clone the repository https://github.com/adwognura/NodeJS_app_docker.git

## Usage

- After installation, run ```npm install``` to download and install all the required dependencies.
- Run ```npm start``` to run the web application.

## Docker build and run
 docker build -t image_name:version .
 docker run -p 3000:3000 -d image_name:version
 
 
