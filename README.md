# Sublime Text 2 Setup/Workflow

My favorite text editor right now is [Sublime Text 2](http://www.sublimetext.com/2). While it does have its limitations, it satisfies most of my needs as a (heavily front-end) web designer/developer.

This project contains a collection of instructions, suggestions, and settings that outline my current Sublime Text 2 workflow, and how you can achieve a similar configuration.

### Table of contents

1. **[Install Sublime Text 2](#install-st2)**

2. **[(Optional) Command Line Utility](#command-line)**

3. **[Install Package Control](#package-control)**

4. **[Themes](#themes)**

	i. [Installing the Soda theme](#install-theme)

5. **[Color Schemes](#schemes)**

	i. [Installing a color scheme](#install-scheme)

6. **[Settings](#settings)**

	i. [Preferences](#settings-preferences)

	ii. [Key Bindings](#settings-bindings)

7. **[Packages](#packages)**

	i. [Advanced New File](#pkg-advancednewfile)

	ii. [Alignment](#pkg-alignment)

	iii. [BracketHighlighter](#pkg-brackethighlighter)

	iv. [Browser Refresh](#pkg-browserrefresh)

	v. [Clipboard History](#pkg-clipboard)

	vi. [Coffeescript](#pkg-coffeescript)

	vii. [CSS Comb](#pkg-csscomb)

	viii. [Detect Syntax](#pkg-detect)

	ix. [Emmet (previously ZenCoding)](#pkg-emmet)

	x. [Emmet CSS Snippets](#pkg-emmet-snippets)

	xi. [Goto Documentation](#pkg-gotodoc)

	xii. [Hex-to-HSL](#pkg-hexhsl)

	xiii. [Hex-to-RGBA](#pkg-hexrgba)

	xiv. [HTML5](#pkg-html5)

	xv. [jQuery](#pkg-jquery)

	xvi. [JsFormat](#pkg-jsformat)

	xvii. [LESS](#pkg-less)

	xviii. [NetTuts+ Fetch](#pkg-fetch)

	xix. [Sass](#pkg-sass)

	xx. [SFTP](#pkg-sftp)

	xxi. [Sidebar Enhancements](#pkg-sidebarenhancements)

8. **[Use Dropbox? Sync your ST2 setup across multiple devices](#sync)**

	i. [Sync up your ST2 projects](#sync-projects)

## <a name="install-st2"></a> Install Sublime Text 2

First thing's first &mdash; you've gotta install the piece. Head on over to [http://www.sublimetext.com/dev](http://www.sublimetext.com/dev), download, and install it on your machine.

## <a name="command-line"></a> (Optional) Command Line Utility

	    sublime [arguments] [files]       - edit the given files
	or: sublime [arguments] [directories] - open the given directories
	or: sublime [arguments]               - edit stdin

If you want to be able to open files with ST2 directly from your terminal window using a custom command (something I do quite often), then [you will want to follow these instructions](https://gist.github.com/1195304).

## <a name="package-control"></a> Install Package Control

Next, you'll definitely want to install [Package Control](http://wbond.net/sublime_packages/package_control), a nifty ST2 plugin that lets you manage ST2 packages directly from ST2's Command Palette (<kbd>Cmd+Shift+P</kbd> for Mac, <kbd>Ctrl+Shift+P</kbd> for Windows/Linux).

To install, bring up the ST2 console (<kbd>Ctrl + `</kbd>), paste in the following code, and hit return:

	import urllib2,os; pf='Package Control.sublime-package'; ipp=sublime.installed_packages_path(); os.makedirs(ipp) if not os.path.exists(ipp) else None; urllib2.install_opener(urllib2.build_opener(urllib2.ProxyHandler())); open(os.path.join(ipp,pf),'wb').write(urllib2.urlopen('http://sublime.wbond.net/'+pf.replace(' ','%20')).read()); print 'Please restart Sublime Text to finish installation'

## <a name="themes"></a> Themes

It's important to note that ST2 "Themes" change the actual look and feel of the software itself. They are not to be confused with "Color Schemes" (explained in the next section), which alter the look and feel of your code within the editor.

The default look of ST2 is really nice, but I wanted a bit more. I've installed the fantastic [Soda Theme by Ian Hill](https://github.com/buymeasoda/soda-theme), and I am very happy with it. I am currently using the "Dark" option.

### <a name="install-theme"></a> Installing the Soda theme

1. Press the <kbd>Cmd+Shift+P</kbd> (or <kbd>Ctrl+Shift+P</kbd> for Windows/Linux) key combination, type "install" into the Command Palette, and select the "Package Control: Install Package" option from the list.

2. Type "soda" to narrow down the list, and select the "Theme - Soda" package (click with mouse or press the Enter key) to install it.

3. To activate the theme, open your User Settings file in `Sublime Text 2 -> Preferences -> Settings - User`, and add the following code (change "Dark" to "Light" if you prefer that one instead):

		{
			"theme": "Soda Dark.sublime-theme"
		}

4. Save your User Settings file, and re-open ST2 to see the changes take effect.

If you aren't a fan of the Soda theme, there are [plenty of other options out there](http://lmgtfy.com/?q=Sublime+Text+2+themes).

## <a name="schemes"></a> Color Schemes

ST2 Color Schemes alter the look and feel of your code, adding syntax highlighting and other goodies. Adding color makes it easier for humans to read and skim through code.

In case you didn't know, **ST2 is compatible with [TextMate themes](http://textmatetheme.com)**.

I am partial to the **Ciapre** theme, which I found [here](http://tmtheme-editor.herokuapp.com/#/Ciapre).

### <a name="install-scheme"></a>Installing a color scheme

To install a color scheme, simply go to `Sublime Text 2 -> Preferences -> Browse Packages`, drop your .tmTheme files into the "Color Scheme - Default" folder, and restart ST2.

To activate the color scheme, just select it from the `Sublime Text 2 -> Preferences -> Color Scheme` folder.

Boom. Done.

## <a name="settings"></a> Settings

One of the beautiful things about ST2 is the flexibility of its settings. You can tweak just about every little aspect of the software to get it working exactly how you want it.

Personally, I am happy with a lot of the default settings that ST2 provides, so my User Settings file is fairly lightweight.

### <a name="settings-preferences"></a> Preferences

1. Open up the Default Settings file and you'll see all the preferences you can tweak. This file can be found by going to `Sublime Text 2 -> Preferences -> Settings - Default`.

2. Also open up the User Settings file, which can be found by going to `Sublime Text 2 -> Preferences -> Settings - User`.

Below is what my current User Settings `Preferences.sublime-settings - User` file looks like:

	{
		"auto_complete_commit_on_tab": true,
		"bold_folder_labels": true,
		"caret_style": "phase",
		"color_scheme": "Packages/Color Scheme - Default/Ciapre.tmtheme",
		"detect_slow_plugins": false,
		"draw_white_space": "all",
		"find_selected_text": true,
		"fold_buttons": false,
		"font_face": "Monaco",
		"font_options":
		[
			"subpixel_antialias"
		],
		"font_size": 14.0,
		"highlight_line": true,
		"ignored_packages":
		[
			"Vintage"
		],
		"line_padding_bottom": 1,
		"line_padding_top": 1,
		"rulers":
		[
			72, 79
		],
		"tab_completion": true,
		"tab_size": 4,
		"theme": "Soda Dark.sublime-theme",
		"translate_tabs_to_spaces": false,
		"trim_trailing_white_space_on_save": true,
		"word_wrap": true
	}

Since I work off a 27" iMac at the office, and a 15" Macbook Pro at home, I find that the Monaco font at size 14 provides a nice, readable experience on both machines.

The `tab_size` and `translate_tabs_to_spaces` options are already "4" and "false" in the Default Settings file, but I added them here because they are some of the more commonly altered options. Also, depending on the project I'm working on, I may have to change those settings on the fly so I don't screw up the spacing for anyone I'm working with.

### <a name="settings-bindings"></a> Key Bindings (Shortcuts)

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
		{ "keys": ["super+alt+n"], "command": "advanced_new_file" },
		{ "keys": ["shift+super+alt+n"], "command": "advanced_new_file", "args": { "is_python": true } },

		// Package - Goto Documentation
		{ "keys": ["ctrl+shift+h"], "command": "goto_documentation" },

		// Package - Hex-to-HSL, convert hex values to HSL
		{ "keys": ["super+shift+h"], "command": "hex_to_hsl" },

		// Package - Hex-to-RGBa, convert hex values to RGBa
		{ "keys": ["super+shift+r"], "command": "hex_to_rgba" },

		// Package - SFTP, setup/edit/browse server commands
		{ "keys": ["ctrl+shift+e"], "command": "sftp_edit_server" },
		{ "keys": ["ctrl+shift+s"], "command": "sftp_browse_server" },
		{ "keys": ["super+ctrl+s"], "command": "sftp_browse" }
	]

## <a name="packages"></a> Packages

Packages are tiny plugins you can install to further enhance your ST2 workflow experience. There are a number of packages that I consider to be essential to my workflow, listed below:

### <a name="pkg-advancednewfile"></a> [Advanced New File](https://github.com/xobb1t/Sublime-AdvancedNewFile) by [Dima Kukushkin](https://github.com/xobb1t/)

Allows you to quickly create new folder structures and files.

#### Key bindings

OSX, Windows, Linux: <kbd>Ctrl+Alt+A</kbd>

* * *

### <a name="pkg-alignment"></a> [Alignment](http://wbond.net/sublime_packages/alignment) by [Will Bond](http://wbond.net/)

Simpler alignment of multi-line selections and multiple selections.

* Align multiple selections to the same column by inserting spaces (or tabs)
* Align all lines in a multi-line selection to the same indent level
* Align the first = on each line of a multi-line selection to the same column

#### Key bindings

Select a chunk of code, or make multiple selections, and press

OSX: <kbd>Cmd+Ctrl+A</kbd>

Windows, Linux: <kbd>Ctrl+Alt+A</kbd>

* * *

### <a name="pkg-brackethighlighter"></a> [BracketHighlighter](https://github.com/facelessuser/BracketHighlighter) by [Isaac Muse](https://github.com/facelessuser)

Adds highlighting of beginning and ending brackets in many programming languages. A huge time saver.

* * *

### <a name="pkg-browserrefresh"></a> [Browser Refresh](http://gcollazo.github.com/BrowserRefresh-Sublime/) by [Giovanni Collazo](https://github.com/gcollazo)

This plugin will switch from ST2 to Google Chrome, Google Chrome Canary, Safari, Firefox or Opera and reload the active tab.

* * *

### <a name="pkg-clipboard"></a> [Clipboard History](https://github.com/kemayo/sublime-text-2-clipboard-history) by [David Lynch](https://github.com/kemayo)

Allows you to copy multiple selections to your clipboard within ST2, to be used interchangeably.

#### Key bindings

To show the clipboard history, press

OSX: <kbd>Cmd+Alt+Ctrl+V</kbd>

Windows, Linux: <kbd>Ctrl+Alt+V</kbd>

* * *

### <a name="pkg-coffeescript"></a> [Coffeescript](https://github.com/Xavura/CoffeeScript-Sublime-Plugin) by [Xavura](https://github.com/Xavura)

A TextMate syntax bundle for Coffeescript.

* * *

### <a name="pkg-csssnippets"></a> [CSS Snippets](https://github.com/joshnh/CSS-Snippets) by [Joshua Hibbert](http://joshnh.com/)

A collection of useful CSS snippets. HUGE TIME SAVER.

If interested, I've created my own fork of this package [here](https://github.com/cbracco/CSS-Snippets).

* * *

### <a name="pkg-csscomb"></a> [CSS Comb](https://github.com/miripiruni/CSScomb-for-Sublime) by [Slava Oliyanchuk](https://github.com/miripiruni)

An amazing package for sorting your CSS properties in a more readable and logical order.

#### Key bindings

Select a chunk of CSS, and press

OSX, Windows Linux: <kbd>Ctrl+Shift+C</kbd>

* * *

### <a name="pkg-detect"></a> [Detect Syntax](https://github.com/phillipkoebbe/DetectSyntax) by [Phillip Koebe](https://github.com/phillipkoebbe)

Helps to decifer the syntax of files that might not otherwise be detected properly.

* * *

### <a name="pkg-emmet"></a> [Emmet](http://docs.emmet.io/) by [Sergey Chikuyonok](https://github.com/sergeche)

An in-editor plugin for high-speed HTML, XML, XSL (or any other structured code format) coding and editing.

* * *

### <a name="pkg-emmet-snippets"></a> [Emmet CSS Snippets](https://github.com/P233/Emmet-Css-Snippets-for-Sublime-Text-2) by [P233](https://github.com/P233)

CSS snippets based on Emmet CSS syntaxes. Works with CSS, LESS, SCSS, and SASS. You can find the full list of snippets [here](https://github.com/P233/Emmet-Css-Snippets-for-Sublime-Text-2/blob/master/Snippets%20List.md).

* * *

### <a name="pkg-gotodoc"></a> [Goto Documentation](https://github.com/kemayo/sublime-text-2-goto-documentation) by [David Lynch](https://github.com/kemayo)

Finds relevant documentation for the function you have your cursor on.

#### Key bindings

Click to place your cursor on a function, and press

OSX, Windows, Linux: <kbd>Ctrl+Shift+H</kbd>

* * *

### <a name="pkg-hexhsl"></a> [Hex-to-HSL](https://github.com/atadams/Hex-to-HSL-Color) by [atadams](https://github.com/atadams)

Converts hexadecimal colors to HSL colors, and visa versa.

#### Key bindings

Click to place your cursor on a hex or HSL value, and press

OSX, Windows, Linux: <kbd>Ctrl+Shift+U</kbd>

* * *

### <a name="pkg-hexrgba"></a> [Hex-to-RGBA](https://github.com/aroscoe/Hex-to-RGBA) by [Anthony Roscoe](https://github.com/aroscoe)

Converts hexadecimal colors to RGBa colors, and visa versa.

#### Key bindings

Click to place your cursor on a hex or RGBa value, and press

OSX: <kbd>Cmd+Shift+R</kbd>

Windows, Linux: <kbd>Ctrl+Shift+R</kbd>

* * *

### <a name="pkg-html5"></a> [HTML5](https://github.com/mrmartineau/HTML5) by [Zander Martineau](http://martineau.tv/)

Adds HTML5 syntax highlighting & relevant snippets to ST2.

* * *

### <a name="pkg-jquery"></a> [jQuery](https://github.com/SublimeText/jQuery) by [Sublime Text](http://www.sublimetext.info/)

jQuery syntax highlighting and snippets for ST2.

* * *

### <a name="pkg-jsformat"></a> [JsFormat](https://github.com/jdc0589/JsFormat) by [Davis Clark](https://github.com/jdc0589)

Javascript syntax highlighting for ST2.

* * *

### <a name="pkg-less"></a> [LESS](https://github.com/danro/LESS-sublime) by [Dan Rogers](http://danro.net/)

LESS syntax highlighting for ST2.

* * *

### <a name="pkg-fetch"></a> [NetTuts+ Fetch](http://net.tutsplus.com/articles/news/introducing-nettuts-fetch/) by [NetTuts+](http://net.tutsplus.com/)

#### Key bindings

Type `fetch` into the Command Palette.

* * *

### <a name="pkg-sass"></a> [Sass](https://github.com/nathos/sass-textmate-bundle) by [Nathan Henderson](http://nathos.com/)

Adds syntax highlighting, indentation, and snippets for Sass and SCSS files.

* * *

### <a name="pkg-sftp"></a> [SFTP](http://wbond.net/sublime_packages/sftp) by [Will Bond](http://wbond.net/)

Commercial SFTP/FTP plugin (free with nag popup) - upload, sync, browse, remote edit, diff, and vcs integration

* * *

### <a name="pkg-sidebarenhancements"></a> [Sidebar Enhancements](https://github.com/titoBouzout/SideBarEnhancements) by [titoBouzout](https://github.com/titoBouzout)

Adds a bunch of new options to the ST2 sidebar, making it exponentially more useful.

* * *

####For more useful ST2 packages, please check out [this GitHub project](https://github.com/mrmartineau/SublimeTextSetup).

## <a name="sync"></a> Use Dropbox? Sync your ST2 setup across multiple devices

Using Dropbox, I keep all of my ST2 settings, snippets, packages, etc synced between all of my machines. So if I'm home working at night and decide I want to change the tab size to 2 spaces, those changes will be reflected on my work computer when I come in the next day. I LOVE THIS.

[Here is the article](http://talltroym.blogspot.com/2012/07/sync-sublime-between-multiple-macs.html) I followed to get this set up correctly.

### <a name="sync-projects"></a> Sync up your local ST2 projects

Also, since I store all of my web files on Dropbox, and both of my machines' admin users share identical names, all of my [ST2 projects](http://www.sublimetext.com/docs/2/projects.html) are synced up as well. This happens because the file paths inside the `.sublime-project` files are identical.

I am not sure if this works the same way on Windows or Linux. I imagine it should.

Here is an example of what one of my saved `.sublime-project` files looks like:

	{
		"folders":
		[
			{
				"path": "/Users/[YOUR_USERNAME]/Dropbox/Development/vhosts/examplesite/"
			}
		]
	}
