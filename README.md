This is a [Sublime Text][sublime] package which includes handy snippets for doing Symfony2 framework development.

## Installation ##

### With Package Control ###

If you have the [Package Control][package_control] package installed, you can install Symfony2 Snippets from inside Sublime Text itself. Open the Command Palette and select "Package Control: Install Package", then search for Symfony2 Snippets.

### Without Package Control ###

If you haven't got Package Control installed you will need to make a clone of this repository into your packages folder, like so:

    git clone https://github.com/raulfraile/sublime-symfony2 symfony2-snippets

## Shortcuts ##

### Controller ###

`sfforward` => $this->forward('TestBundle:Folder:view', array());

[sublime]: http://www.sublimetext.com/
[package_control]: http://wbond.net/sublime_packages/package_control