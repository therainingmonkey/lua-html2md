 # lua-html2md
 
 A simple module to convert from html to markdown,
 mainly using Lua's text substitutions.
 
 ### Usage:
 ```lua
 html2md = require "html2md"
 
 html = "<html><b>Hello,</b> <i>world!</i></html>"
 markdown = html2md:parse(html)
 print(markdown) -- "**Hello,** _world!_"
 ```
 html2md takes an optional second argument to hide urls. If this argument
 is `true`, the markdown does not contain urls, only link text.
 
 You can also call `html2md.parsefile()` which takes a filename in the same
 format as `io.open()`. This also takes the optional argument to hide urls.
 
 
 ### TODO:
 * preserve whitespace in code blocks
 * continue ordered list numbering after it's interrupted by a nested list (current behaviour is valid md, but less readable)
 * emphasis can be mangled by linebreaks
 * all headers are currently treated as h1
