# Sublime Text 2 Setup/Workflow

My favorite text editor right now is [Sublime Text 2](http://www.sublimetext.com/2). While it does have its limitations, it satisfies most of my needs as a (heavily front-end) web designer/developer. 

This project contains a collection of instructions, suggestions, and settings that outline my current Sublime Text 2 workflow, and how you can achieve a similar configuration.

## Install Sublime Text 2

First thing's first &mdash; you've gotta install the piece. Head on over to [http://www.sublimetext.com/dev](http://www.sublimetext.com/dev), download, and install it on your machine.

## Command Line Utility (optional)

	    sublime [arguments] [files]       - edit the given files
	or: sublime [arguments] [directories] - open the given directories
	or: sublime [arguments]               - edit stdin

If you want to be able to open files with ST2 directly from your terminal window using a custom command (I use "sublime [folderpath/file name]"), then [you will want to follow these instructions](https://gist.github.com/1195304).

## Install Package Control

Next, you'll definitely want to install [Package Control](http://wbond.net/sublime_packages/package_control), a nifty ST2 plugin that lets you manage ST2 packages directly from ST2's Command Palette (⌘+Shift+P for Mac, Ctrl+Shift+P for PC).

## Themes

It's important to note that ST2 "Themes" change the actual look and feel of the software itself. They are not to be confused with "Color Schemes" (explained in the next section), which alter the look and feel of your code within the editor. 

The default look of ST2 is really nice, but I wanted a bit more. I've installed the fantastic [Soda Theme by Ian Hill](https://github.com/buymeasoda/soda-theme), and I am very happy with it. I am currently using the "Dark" option.

### Installing the Soda theme

1. Press the ⌘+Shift+P (or Ctrl+Shift+P for PC) key combination, type "install" into the Command Palette, and select the "Package Control: Install Package" option from the list.
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

**To install a color scheme**, simply go to `Sublime Text 2 -> Preferences -> Browse Packages`, drop your .tmTheme files into the "Color Scheme - Default" folder, and restart ST2.

**To change your color scheme** in ST2, just select one from the folder located in `Sublime Text 2 -> Preferences -> Color Scheme`.

## Settings

One of the beautiful things about ST2 is the flexibility of its settings. You can tweak just about every little aspect of the software to get everything exactly how you want it.

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

### Key Bindings

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



## Use Dropbox? Sync your ST2 setup across multiple devices