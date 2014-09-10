# Compatibility tables data

This repository contains the raw data served by the [WebPlatform project](http://www.webplatform.org/) at [docs.webplatform.org/compat/data.json](http://docs.webplatform.org/compat/data.json).

To learn more about how the data is used, refer to [WebPlatform Docs Infrastructure CompaTables Component](http://docs.webplatform.org/wiki/WPD:Infrastructure/Components/CompaTables)


## To use

Under a GNU/Linux or MacOS, you can use it as a NPM module.


### Install

There’s nothing much to install to contribute. The `package.json` will make you install `underscore-cli` that can be (optionally) used to query and validate the JSON file.

    npm install

### Change data

Edit the `data-human.json` following the same format, commit and make a pull request.

### Checking data

You can use the awesome [underscore-cli](https://github.com/ddopson/underscore-cli) to query and validate the JSON from the command line.

Here are a few useful commands:

#### What data has Feature X

In our case, we want to find the feature "use_strict", in the "javascript" topic.

    cat data-human.json | underscore extract 'data.javascript.use_strict'
    {
      "breadcrumb": ["javascript", "reference", "use_strict"],
      "jsonselect": ":root > .data > .javascript > .use_strict",
      "contents": {
        "desktop": {
          "Basic support": {
            "Chrome": { "?": "y" },
            "Firefox": { "21": "y" },
            "Internet Explorer": { "10": "y" },
            "Opera": { "12": "y" },
            "Safari": { "6": "y" }
          }
        },
        "mobile": { }
      },
      "links": [
        {
          "title": "ECMAScript 5 compatibility table",
          "url": "http://kangax.github.io/compat-table/es5/#Strict_mode"
        }
      ]
    }

