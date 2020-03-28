# gdoc-links-replacer

[![Build Status](https://travis-ci.org/joemccann/dillinger.svg?branch=master)](https://travis-ci.org/joemccann/dillinger)

Author: Agustin Bassi
Date: April 2020

Tool for avoid "Redirect Notice" in Google Docs links when export it as PDF or HTML format.

## Project motivation

This file serves to eliminate redirect notice when press documents links when a Google Doc is exported as PDF or HTML File.

To tracks all interaction between a Google Doc and their links, Google appends to all of them the prefix LINK_PREFIX_PATTERN and also appends a LINK_SUFFIX_PATTER with a series of number (timestamp).

This python tool scans recursively a directory passed by script argument, try to find FILE_NAMES_TO_UPDATE in each subdirectory, and if it founds them update the content of each LINK_PREFIX_PATTERN to LINK_PREFIX_REPLACER and the content of each LINK_SUFFIX_PATTERN to LINK_SUFFIX_REPLACER

## Usage

Example of use:

```sh
$ python links_replacer.py absolute_path_where_posts_are
```
## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)