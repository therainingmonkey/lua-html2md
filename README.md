 # lua-html2md

 A simple module to convert from html to markdown,
 mainly using Lua's text substitutions.

 ### Usage:
 ```lua
 html2md = require "html2md"

 html = "<html><b>Hello,</b> <i>world!</i></html>"
 markdown = html2md.parse(html)
 print(markdown) -- "**Hello,** _world!_"
 ```
 `parse` takes an optional second argument to change how URLs are rendered in links.
 options are:
 * `show` (default) - normal behaviour: [inline links](example.com)
 * `hide` - No URLs shown: [Just link text]
 * `footnote` - Reference-style links with the URL at the [bottom][1] of the page.

 You can also call `html2md.parseFile()` which takes a filename in the same
 format as `io.open()`. This also takes the optional second argument.

[1]: http://einchan.god.jp

 ### TODO:
 * continue ordered list numbering after it's interrupted by a nested list (current behaviour is valid md, but less readable)
 * emphasis can be mangled by linebreaks
 * all headers are currently treated as h1
