---
title: "Basic Syntax Highlighting Using Swift"
layout: default
---

For one of my projects I wanted syntax highlighting for code loaded from repositories. I figured it was common enough in many projects and that there would be a library that would handle the job nicely. To my surprise there were only a few, and none are well supported. Of those found none have been updated in over a year. In Swift years this is very long which means if a project is to be salvaged one must migrate from Swift 2 or version 1 in some cases. I felt that instead of trying to salvage one these I would a nice little Sunday project to build my own.  
Here is the Syntax Highlighter on some of my Objective-C code with the "Obsidian" theme.

Let's go over the few requirements I had for my project:

Simplistic design
Generic grammars that support more than one language 
Decent performance
Customizable colour schemes
Based on my requirements I decided I wanted to go for a generic parser that would handle any C-Like language reasonably well with most relevant tokens, comments etc highlighted. This is important to me since the application this will be used in will load code from repositories of any language so it must handle the majority.

The first step was to produce a simple Lexer that detects keywords, symbols, and comments and emits them as tokens. These tokens are then used to colour an NSAttributedString that is displayed in a text container. The solution is extensible though the use of dictionaries that specify language keywords, comments, strings, symbols etc. Additionally colour schemes are created though dictionaries for the token types and extend to their container foreground. The project can be seen below, with the demo project on GitHub. I'd say the project is pretty good for the few hours spent on it and it does seem to handle the few C-Like languages that I've thrown at it.
