Node.js Web Scraper

Goal: Create a command line program that can parse remote pages, read the html, and write the content that we care about to a file on disk.

Duration: You should aim to have this project completed by the end of the day.

Reminders:

Please create your own git repository on github
Commit and push your progress on a regular basis.
Project:

Create a node module to parse a remote webpage

Now that you understand the basics, it’s time to create your very own node module. We will use npm to install third party modules that we can use from the command line or as part of our own module. We will also use npm to manage our modules third party dependencies.

Then we will create our own program/module that runs inside our terminal using node. The module will be designed make HTTP GET requests to remote web pages and download their HTML. We will then (using another module) parse the HTML and write the content we are interested in to a file on disk.

WHAT? We are basically building a simplified web scraper... Watch out Google!

Setup:

Create a new directory inside your (vagrant) workspace for this exercise. Create/open the .gitignore file and add a line with the text node_modulesto it so that third party modules are not checked into your repo.

To start a module you need to have a package.jsonfile. It should be thought of as the manifest for your module. Modules generally depend on other modules to get the job done. Anytime you install a third party npm module, npm will list it in this manifest package.json file. This ensures that the next person to use your program (module) can simply run npm install to get all the dependencies for it. This is very much like a Gemfile for Ruby’s Bundler.

To initialize your module with a package.json simply run:

$ npm init
This is again similar to bundle initwhich initializes a Gemfile in a ruby project. You will answer a series of questions and npm will create a package.json for you.

This project will require two third party npm modules;

request allows us to create HTTP clients even easier. It has a simpler API than the http module (which also allows us to make HTTP requests).
cheerio will take the downloaded HTML and using jQuery syntax we can extract the information that we need.
Don’t install them just yet (instructions below). But do go ahead and browse their README on github to understand what they do and how they do it.

Whilst inside your project directory run the following command to install these modules and save them to your package.json:

npm install ­­save request cheerio
Note how your package.json file is modified and the npm_modules folder now contains those 3rd party modules.

Now using these modules, we will create a module that will make an HTTP GET request to http://substack.net/images/, parse the page’s html and write a file to disk called images.csv that has 3 columns populated from the remote html. The columns should be:

File Permission
Absolute URL
File Type
In case you have forgotten about them, you can read up on Comma Separated Values (CSV) files on Wikipedia.

Note: If this module was actually something you wanted to release to the node community through npm you would want to look at “npm publish” which allows you to publish your module to npm’s registry for others to install and use. Cool right?

Important Tips:

Work incrementally (using console.log to test as you go) Use node CLI REPLY (like irb) to play around with the modules interactively You’ll also need to use the fs module (built into node) to write the data to a csv file.