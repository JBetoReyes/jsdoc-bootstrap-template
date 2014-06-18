JSDoc Bootstrap Template
========================

The default [JSDoc](http://usejsdoc.org) template is fairly bland, so I took it upon myself to create a custom template using the marvelous [Bootstrap](http://getbootstrap.com/) library. There were a couple of other Bootstrap-based templates out there before I began this project, but none of them satisfied my needs. This template uses Bootsrap 2, but eventually will be upgraded to Bootstrap 3.

The default template for JSDoc3 uses: [the Taffy Database library](http://taffydb.com/) and the [Underscore Template library](http://documentcloud.github.com/underscore/#template).


Installation
------------

It is probably a good idea to clone this repo into some easily-accessible location (perhaps you already have a folder full of repositories?) and then __symlink__ the folder into the JSDoc templates directory. However, you may choose to clone this repo directly into the JSDoc folder. Just be aware, if you choose the second method, that the repo might disappear if you ever uninstall or upgrade JSDoc! For the purposes of this README, it will be assumed that you will be cloning and then symlinking the repo.

    :::bash
    # wherever you're putting it...
    $ cd "$some_workspace_path"
    $ git clone git@bitbucket.org:Smolations/jsdoc-bootstrap-template.git

Now you're ready to install JSDoc and import the template. JSDoc3 can be installed in two different ways:


### via homebrew (recommended for Mac OS X machines)

Open your Terminal and do the following:

    :::bash
    # update homebrew
    $ brew update

    # install JSDoc3. current version at the time of this writing is 3.2.2.
    $ brew install jsdoc3

    # tell homebrew NOT to update this module when the author updates the
    # version. this ensures compatibility. if this is not done, you will need
    # to symlink the template repo into each installed version's templates directory
    $ brew pin jsdoc3

Homebrew installs software (by default) in `/usr/local/Cellar`. The template contents defined in this repository must live inside of the JSDoc install directory. In order to keep the template repo more visible and accessible (and safe from accidental deletion), create a symlink from the repo into the JSDoc templates folder:

    :::bash
    # now we can create the symlink (-s option means symlink or "soft" link)
    # usage:  ln -s <existing> <symlink_destination>
    $ ln -s "${some_workspace_path}jsdoc-bootstrap-template" /usr/local/Cellar/jsdoc3/3.2.2/libexec/templates/bootstrap

    # the template folder is symlinked as `bootstrap` above, but it can be
    # whatever you want (since it's just a symlink!)


### via npm (**must** use this for Windows, but works with other platforms too)

`npm` is Node's package manager. I generally prefer to use `npm` only when a package can ONLY be installed via `npm` (like LESS and JSHint). However, some packages were written for node.js and then ported to other platforms. In these cases I install the package using `npm`.

1. Install JSDoc (globally). Its dependencies will be installed automatically:
    * `npm install -g jsdoc@3.2.2`

Unfortunately, `npm` doesn't have the same "pin" mechanism that homebrew has to lock down the version. Therefore, try to **never** run only `$ npm update` as it will update any modules which have been upgraded. Instead, only update specific modules which require it by specifying the module on the command line (e.g.): `$ npm update -g bless`

Depending on your operating system, the location of the global `node_modules` will vary. You can find this information out if your un `$ npm list -g` (note that the node_modules folder is omitted from the output, but each module is located within that folder). Please verify before moving forward:

- Mac OS X:  `/usr/local/lib/node_modules`
- Windows:  `~/AppData/Roaming/npm/node_modules`

In Windows, symlinking isn't as straight forward. However, we want to keep the repo in a separate location, so it's beneficial.

1. Open the Start menu and type "cmd" if your version permits, or navigate to All Programs -> Accessories -> Command Prompt. DON'T CLICK YET!
2. Right-Click on the program and select "Run As Administrator"
3. To get the paths just right, you should use a text editor to alter the paths. Since we're using cmd.exe, we must use Windows commands/paths. Below is an example of the most common usage (> replaces $ prompt for Windows):
    * `> mklink /d "C:\Users\Smolations\AppData\Roaming\npm\node_modules\jsdoc\templates\bootstrap" "C:\Users\Smolations\workspaces\jsdoc-bootstrap-template"`

You can verify that the symlink worked by using Windows Explorer and navigating to the JSDoc templates directory. There should be a shortcut named `bootstrap` (or whatever __you__ named it) that should provide access to the files in this repo.


Usage
-----

You can choose to specify the new template in a JSDoc configuration file (e.g. `conf.json`) or on the command line. See the [JSDoc](http://usejsdoc.org) documentation for examples.


Conclusion
----------
Be sure to keep the JSDoc documentation handy while writing your comments! Happy commenting!
