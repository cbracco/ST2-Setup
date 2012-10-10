# Sublime Text 2 Setup/Workflow

My favorite text editor right now is [Sublime Text 2](http://www.sublimetext.com/2). While it does have its limitations, it satisfies most of my needs as a (heavily front-end) web designer/developer. 

This project contains a collection of instructions, suggestions, and settings that outline my current Sublime Text 2 workflow, and how you can achieve a similar configuration.

## Install Sublime Text 2

First thing's first &mdash; you've gotta install the piece. Head on over to [http://www.sublimetext.com/dev](http://www.sublimetext.com/dev), download, and install it on your machine.

## (Optional) Command Line Utility

	    sublime [arguments] [files]       - edit the given files
	or: sublime [arguments] [directories] - open the given directories
	or: sublime [arguments]               - edit stdin

If you want to be able to open files with ST2 directly from your terminal window using a custom command (something I do quite often), then [you will want to follow these instructions](https://gist.github.com/1195304).

## Install Package Control

Next, you'll definitely want to install [Package Control](http://wbond.net/sublime_packages/package_control), a nifty ST2 plugin that lets you manage ST2 packages directly from ST2's Command Palette (`Cmd+Shift+P` for Mac, `Ctrl+Shift+P` for Windows/Linux).

To install, bring up the ST2 console (``Ctrl + ` ``), paste in the following code, and hit return:

	import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print 'Please restart Sublime Text to finish installation'

## Themes

It's important to note that ST2 "Themes" change the actual look and feel of the software itself. They are not to be confused with "Color Schemes" (explained in the next section), which alter the look and feel of your code within the editor. 

The default look of ST2 is really nice, but I wanted a bit more. I've installed the fantastic [Soda Theme by Ian Hill](https://github.com/buymeasoda/soda-theme), and I am very happy with it. I am currently using the "Dark" option.

### Installing the Soda theme

1. Press the `Cmd+Shift+P` (or `Ctrl+Shift+P` for Windows/Linux) key combination, type "install" into the Command Palette, and select the "Package Control: Install Package" option from the list.

2. Type "soda" to narrow down the list, and select the "Theme - Soda" package (click with mouse or press the Enter key) to install it.

3. To activate the theme, open your User Settings file in `Sublime Text 2 -> Preferences -> Settings - User`, and add the following code (change "Dark" to "Light" if you prefer that one instead):

		{ 
			"theme": "Soda Dark.sublime-theme"
		}

4. Save your User Settings file, and re-open ST2 to see the changes take effect.

If you aren't a fan of the Soda theme, there are [plenty of other options out there](http://lmgtfy.com/?q=Sublime+Text+2+themes).

## Color Schemes

ST2 Color Schemes alter the look and feel of your code, adding syntax highlighting and other goodies. Adding color makes it easier for humans to read and skim through code.

In case you didn't know, **ST2 is compatible with [TextMate themes](http://textmatetheme.com)**. 

I am partial to the [Made Of Code](http://textmatetheme.com/made-of-code) TextMate theme, which works very nicely in the ST2 enviornment and looks great combined with the dark Soda theme.

### Installing a color scheme

To install a color scheme, simply go to `Sublime Text 2 -> Preferences -> Browse Packages`, drop your .tmTheme files into the "Color Scheme - Default" folder, and restart ST2.

To activate the color scheme, just select it from the `Sublime Text 2 -> Preferences -> Color Scheme` folder. 

Boom. Done.

## Settings

One of the beautiful things about ST2 is the flexibility of its settings. You can tweak just about every little aspect of the software to get it working exactly how you want it.

Personally, I am happy with a lot of the default settings that ST2 provides, so my User Settings file is fairly lightweight.

### Preferences

1. Open up the Default Settings file and you'll see all the preferences you can tweak. This file can be found by going to `Sublime Text 2 -> Preferences -> Settings - Default`.

2. Also open up the User Settings file, which can be found by going to `Sublime Text 2 -> Preferences -> Settings - User`.

Below is what my current User Settings `Preferences.sublime-settings - User` file looks like:

	{
		"auto_complete_commit_on_tab": true,
		"color_scheme": "Packages/Color Scheme - Default/Made of Code.tmTheme",
		"font_face": "Monaco",
		"font_size": 14.0,
		"ignored_packages":
		[
			"Vintage"
		],
		"tab_size": 4,
		"translate_tabs_to_spaces": false,
		"theme": "Soda Dark.sublime-theme",
		"word_wrap": true
	}

Since I work off a 27" iMac at the office, and a 15" Macbook Pro at home, I find that the Monaco font at size 14 provides a nice, readable experience on both machines.

The `tab_size` and `translate_tabs_to_spaces` options are already "4" and "false" in the Default Settings file, but I added them here because they are some of the more commonly altered options. Also, depending on the project I'm working on, I may have to change those settings on the fly so I don't screw up the spacing for anyone I'm working with.

### Key Bindings (Shortcuts)

To help speed up your workflow, ST2 provides a ton of built-in key bindings, or keyboard shortcuts. As you've probably guessed, you can also create your own custom keyboard shortcuts.

1. Open up the Default Key Bindings file and you'll see all the available keyboard shortcuts. This file can be found by going to `Sublime Text 2 -> Preferences -> Key Bindings - Default`.
2. Also open up the User Key Bindings file, which can be found by going to `Sublime Text 2 -> Preferences -> Key Bindings - User`.

Below is what my current User Key Bindings `Default (OSX).sublime-keymap - User` file looks like:

	[
		// Refresh settings & folder list
		{ "keys": ["super+ctrl+r"], "command": "settings_refresh" },
		{ "keys": ["alt+ctrl+r"], "command": "refresh_folder_list" },

		// Toggle sidebar visibility
		{ "keys": ["ctrl+s"], "command": "toggle_side_bar" },

		// Package - Advanced New File
		{ "keys": ["super+alt+n"], "command": "advanced_new_file"},
		{ "keys": ["shift+super+alt+n"], "command": "advanced_new_file", "args": {"is_python": true}},

		// Package - Goto Documentation
		{ "keys": ["ctrl+shift+h"], "command": "goto_documentation" },

		// Package - Hex-to-HSL, convert hex values to HSL
		{ "keys": ["super+shift+h"], "command": "hex_to_hsl" },

		// Package - Hex-to-RGBa, convert hex values to RGBa
		{ "keys": ["super+shift+r"], "command": "hex_to_rgba" },

		// Package - SFTP, browse server of current file
		{ "keys": ["super+ctrl+s"], "command": "sftp_browse" }
	]

## Packages

Packages are tiny plugins you can install to further enhance your ST2 workflow experience. There are a number of packages that I consider to be essential to my workflow, listed below:

### [Advanced New File](https://github.com/xobb1t/Sublime-AdvancedNewFile) by [Dima Kukushkin](https://github.com/xobb1t/)

Allows you to quickly create new folder structures and files.

#### Key bindings

OSX, Windows, Linux: `Ctrl+Alt+A`

### [Alignment](http://wbond.net/sublime_packages/alignment) by [Will Bond](http://wbond.net/)

Simpler alignment of multi-line selections and multiple selections.

* Align multiple selections to the same column by inserting spaces (or tabs)
* Align all lines in a multi-line selection to the same indent level
* Align the first = on each line of a multi-line selection to the same column

#### Key bindings

Select a chunk of code, or make multiple selections, and press

OSX: `Cmd+Ctrl+A`
Windows, Linux: `Ctrl+Alt+A`

### [BracketHighlighter](https://github.com/facelessuser/BracketHighlighter) by [Isaac Muse](https://github.com/facelessuser)

Adds highlighting of beginning and ending brackets in many programming languages. A huge time saver.

### [Clipboard History](https://github.com/kemayo/sublime-text-2-clipboard-history) by [David Lynch](https://github.com/kemayo)

Allows you to copy multiple selections to your clipboard within ST2, to be used interchangeably.

#### Key bindings

To show the clipboard history, press

OSX: `Cmd+Alt+Ctrl+V`
Windows, Linux: `Ctrl+Alt+V`

### [Coffeescript](https://github.com/Xavura/CoffeeScript-Sublime-Plugin) by [Xavura](https://github.com/Xavura)

A TextMate syntax bundle for Coffeescript.

### [CSS Snippets](https://github.com/joshnh/CSS-Snippets) by [Joshua Hibbert](http://joshnh.com/)

A collection of useful CSS snippets. HUGE TIME SAVER.

If interested, I've created my own fork of this package [here](https://github.com/cbracco/CSS-Snippets).

### [CSS Comb](https://github.com/miripiruni/CSScomb-for-Sublime) by [Slava Oliyanchuk](https://github.com/miripiruni)

An amazing package for sorting your CSS properties in a more readable and logical order.

#### Key bindings

Select a chunk of CSS, and press

OSX, Windows Linux: `Ctrl+Shift+C`

### [Detect Syntax](https://github.com/phillipkoebbe/DetectSyntax) by [Phillip Koebe](https://github.com/phillipkoebbe)

Helps to decifer the syntax of files that might not otherwise be detected properly.

### [Goto Documentation](https://github.com/kemayo/sublime-text-2-goto-documentation) by [David Lynch](https://github.com/kemayo)

Finds relevant documentation for the function you have your cursor on.

#### Key bindings

Click to place your cursor on a function, and press

OSX, Windows, Linux: `Ctrl+Shift+H`

### [Hex-to-HSL](https://github.com/atadams/Hex-to-HSL-Color) by [atadams](https://github.com/atadams)

Converts hexadecimal colors to HSL colors, and visa versa.

#### Key bindings

Click to place your cursor on a hex or HSL value, and press

OSX, Windows, Linux: `Ctrl+Shift+U`

### [Hex-to-RGBA](https://github.com/aroscoe/Hex-to-RGBA) by [Anthony Roscoe](https://github.com/aroscoe)

Converts hexadecimal colors to RGBa colors, and visa versa.

#### Key bindings

Click to place your cursor on a hex or RGBa value, and press

OSX: `Cmd+Shift+R`
Windows, Linux: `Ctrl+Shift+R`

### [HTML5](https://github.com/mrmartineau/HTML5) by [Zander Martineau](http://martineau.tv/)

Adds HTML5 syntax highlighting & relevant snippets to ST2.

### [jQuery](https://github.com/SublimeText/jQuery) by [Sublime Text](http://www.sublimetext.info/)

jQuery syntax highlighting and snippets for ST2.

### [JsFormat](https://github.com/jdc0589/JsFormat) by [Davis Clark](https://github.com/jdc0589)

Javascript syntax highlighting for ST2.

### [LESS](https://github.com/danro/LESS-sublime) by [Dan Rogers](http://danro.net/)

LESS syntax highlighting for ST2.

### [NetTuts+ Fetch](http://net.tutsplus.com/articles/news/introducing-nettuts-fetch/) by [NetTuts+](http://net.tutsplus.com/)

#### Key bindings

Type `fetch` into the Command Palette.

### [Sass](https://github.com/nathos/sass-textmate-bundle) by [Nathan Henderson](http://nathos.com/)

Adds syntax highlighting, indentation, and snippets for Sass and SCSS files.

### [SFTP](http://wbond.net/sublime_packages/sftp) by [Will Bond](http://wbond.net/)

Commercial SFTP/FTP plugin (free with nag popup) - upload, sync, browse, remote edit, diff, and vcs integration

### [Sidebar Enhancements](https://github.com/titoBouzout/SideBarEnhancements) by [titoBouzout](https://github.com/titoBouzout)

Adds a bunch of new options to the ST2 sidebar, making it exponentially more useful.

### [SublimeCodeIntel](https://github.com/Kronuz/SublimeCodeIntel) by [Germán M. Bravo](https://github.com/Kronuz)

Provides auto-completion information in real-time, and function call tooltips.

### [ZenCoding](https://bitbucket.org/sublimator/sublime-2-zencoding) by [Nicholas Dudfield](https://bitbucket.org/sublimator/)

An editor plugin for high-speed HTML, XML, XSL (or any other structured code format) coding and editing.

**For more useful ST2 packages, please check out [this GitHub project](https://github.com/mrmartineau/SublimeTextSetup).**

## Use Dropbox? Sync your ST2 setup across multiple devices

Using Dropbox, I keep all of my ST2 settings, snippets, packages, etc synced between all of my machines. So if I'm home working at night and decide I want to change the tab size to 2 spaces, those changes will be reflected on my work computer when I come in the next day. I LOVE THIS.

[Here is the article](http://andrew.hedges.name/blog/2012/01/19/sublime-text-2-more-sublime-with-a-drop-of-dropbox) I followed to get this all set up.

### Sync up your ST2 projects

Also, since I store all of my web files on Dropbox, and both of my machines' admin users share identical names, all of my [ST2 projects](http://www.sublimetext.com/docs/2/projects.html) are synced up as well. This happens because the file paths inside the `.sublime-project` files are identical.

I am not sure if this works the same way on Windows or Linux. I imagine it should.

Here is an example of what one of my saved `.sublime-project` files looks like:

	{
		"folders":
		[
			{
				"path": "/Users/[ADMIN_USERNAME]/Dropbox/Sites/examplesite/"
			}
		]
	}
