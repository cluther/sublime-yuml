yUML for Sublime Text
=====================

Makes using [yUML](http://yuml.me/) from Sublime Text easier. Making two great tools better by making them work together.

Sublime Text 2 and 3 on all platforms should be supported.


Features
========

There are currently only two (2) features, but they're the features you want.

* Syntax highlighting for *.yuml files.
![Syntax Highlighting](https://raw.github.com/cluther/sublime-yuml/develop/images/syntax_highlighting.png)

* Open image for diagram in browser.
![Open Diagram in Browser](https://raw.github.com/cluther/sublime-yuml/develop/images/open_diagram_in_browser.png)


Install
=======

Please use [Package Control](https://sublime.wbond.net/). You'll be happier that way unless you plan on hacking on the code.

1. Package Control: Install Package
2. Install "yUML"


Usage
=====

Syntax highlighting will automatically be done for files with a .yuml extension. For files with different extensions, you will have to set the syntax yourself.

To open your diagram in your default browser, open the command palette with
`super-shift-p` then search for `yuml diagram` and select *yUML: Open Diagram
in Browser*.

To change the diagram settings, open the command palette with `super-shift-p`
then search for `yuml user` and select *Preferences: yUML Settings - User*.
This will open your user settings for yUML. This is a JSON file which can
contain overrides of the following default settings.

```json
{
	/*
	 * Default diagram type.
	 *
	 * Valid options: activity, class, usecase
	 */
	"default_type": "class",

	/*
	 * Default output file type.
	 *
	 * Valid options: jpg, json, pdf, png, svg
	 */
	"default_extension": "png",

	/*
	 * Default diagram style.
	 *
	 * Valid optins: nofunky, plain, scruffy
	 */
	"default_style": "scruffy",

	/*
	 * Default diagram orientation.
	 *
	 * Valid options:
	 *   LR = Left-to-right
	 *   TB = Top-to-bottom
	 *   RL = Right-to-left
	 */
	"default_dir": "LR",

	/*
	 * Default output scale where applicable.
	 *
	 * Valid options:
	 *    60 = Tiny
	 *    80 = Small
	 *   100 = Normal
	 *   120 = Big
	 *   180 = Huge
	 */
	"default_scale": "100",
}
```


Caveats
=======

It has come to my attention that diagrams that encode to URIs longer than 4096
characters will not work. I've made a clear error message to indicate this is a
problem in version 1.0.1, but am looking to switch to POST request instead of
GET requests in a future version to supporter larger diagrams.
