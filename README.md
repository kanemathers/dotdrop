dotdrop
=======

Easily sync dotfiles between computers

Plugins
-------

Plugins are simply folders within the `plugins.d` folder. The individual
plugin folders contain the files/directories you want symlinked to your
$HOME.

For example:

    $ ls ./plugins.d/vim
    vim vimrc

When dotdrop runs, those files will be symlinked to $HOME:

    $ ls -la ~/.vim*
    .vim -> /home/kane/dotdrop/plugins.d/vim/vim
    .vimrc -> /home/kane/dotdrop/plugins.d/vim/vimrc

Usage
-----

1. Clone dotdrop into a folder you have synchronized between devices. This
   could be your Dropbox folder, BTSync folder, etc.

        $ git clone https://github.com/kanemathers/dotdrop.git ~/

2. Run dotdrop:

        $ ~/dotdrop/dotdrop

3. dotdrop should be run on startup to ensure your local symlinks keep in
   sync with your plugins:

        $ echo "[ -f ~/dotdrop/dotdrop ] && . ~/dotdrop/dotdrop" >> ~/.bash_profile

    Substitute ``~/dotdrop`` for your actual path. In this example,
    ``~/dotdrop`` is shared between computers via BTSync.

Configuration
-------------

Environment variables are used to configure dotdrop.

`DOTDROP_NOFIFY` - default: "no" - Enable notifications.
