# isearch #

Python and AppleScript for searching the iTunes, App, and Mac App Stores and creating Markdown reference affiliate links.

## Dependencies ##

* [python-itunes][2] for implementing the [iTunes Search API][3] in Python.
* [CocoaDialog][1] for showing multiple search results.

## isearch ##

A Python script that takes a search string as an argument and returns the URL of a match. It finds the top 25 matches for the search string and presents them to the user in a dropdown menu. Whichever item the user selects is the one whose URL is returned.

Because the iTunes stores are so big, the search can be limited to specific media types through command line options:

* `-m` or `--mac`: Mac software only
* `-i` or `--ios`: iOS software only
* `-s` or `--song`: Songs only
* `-a` or `--album`: Albums only
* `-b` or `--book`: Ebooks only
* `-f` or `--movie`: Movies only


If no option is provided, a generic search is performed, which typically isn't very useful.


## iTunes Search Link ##

An AppleScript for use with [BBEdit][4] to create [Markdown reference-style affiliate links][5] to items in iTunes, App, or Mac App Stores. It takes the current selection as the search string, asks the user which media type to search for, and calls `isearch` to present the search results to the user. After the user chooses, the selected text is turned into a link with a numbered reference at the bottom of the page.

`iTunes Search Link` should be put in BBEdit's Scripts folder. It expects to find `isearch`, `bbstdin`, and `nextreflink` in `~/Dropbox/bin`.

## bbstin and nextreflink ##

Helper scripts that allow `iTunes Search Link` to work. Described in detail [here][6].




[1]: http://mstratman.github.io/cocoadialog/
[2]: https://github.com/drdrang/python-itunes
[3]: http://www.apple.com/itunes/affiliates/resources/documentation/itunes-store-web-service-search-api.html
[4]: https://itunes.apple.com/us/app/bbedit/id404009241?mt=12&uo=4&at=10l4Fv
[5]: http://daringfireball.net/projects/markdown/syntax
[6]: http://www.leancrew.com/all-this/2012/08/markdown-reference-links-in-bbedit/
