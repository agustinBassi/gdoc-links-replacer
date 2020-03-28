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

There are many ways of usage depending on what is desired.

The only needed (and obligatory) argument is a positional one with the folder where files with to be replaced with the links replacer are.

The best way to discover how to run the tool is executing its help with the command below:

```sh
$ python links_replacer.py -h
```
An output like this will apear on the console:

```sh
$ python links_replacer.py -h
usage: links_replacer.py [-h] [-v] [-d]
                         [--files-to-replace [files-to-replace [files-to-replace ...]]]
                         [--link-prefix-pattern link-prefix-pattern]
                         [--link-suffix-pattern link-suffix-pattern]
                         [--link-prefix-replacer link-prefix-replacer]
                         [--link-suffix-replacer link-suffix-replacer]
                         [--file-suffix-backup file-suffix-backup]
                         input-dir

Help of usage for Google Docs link replacer tool by Agustin Bassi

positional arguments:
  input-dir             The absolute path where folder with Exported Google
                        Docs are

optional arguments:
  -h, --help            show this help message and exit
  -v, --verbosity       Set the verbosity level of application
  -d, --debug           Set debug level to logging module
  --files-to-replace [files-to-replace [files-to-replace ...]]
                        The list of files that the tool will try to find to
                        replace its links
  --link-prefix-pattern link-prefix-pattern
                        The preffix pattern which links are prefixed by the
                        Google Docs export tool
  --link-suffix-pattern link-suffix-pattern
                        The suffix pattern which links are suffixed by the
                        Google Docs export tool
  --link-prefix-replacer link-prefix-replacer
                        The content that will be replaced when tool finds the
                        --link-prefix-pattern
  --link-suffix-replacer link-suffix-replacer
                        The content that will be replaced when tool finds the
                        --link-suffix-pattern
  --file-suffix-backup file-suffix-backup
                        The suffix that will be appended to orinal(s) files-
                        to-replace to save them as a backup
```

The main common use is only passing the path where files to be replaced are like the command below:

```sh
$ python links_replacer.py absolute_path_where_posts_are
```

There are many other option (like showed in help output) that only be passed to the tool if the prefix/suffix or Google Docs links change. For the rest of the cases the command above must be sufficient.


## Contributing

Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License

[MIT](https://choosealicense.com/licenses/mit/)