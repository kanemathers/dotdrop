dotdrop
=======

Keep your dotfiles nsync with the dropbox as the backup dancer.

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
    .vim -> /home/kane/Dropbox/dotdrop/plugins.d/vim/vim
    .vimrc -> /home/kane/Dropbox/dotdrop/plugins.d/vim/vimrc

Usage
-----

1. Clone dotdrop into your Dropbox folder:

        $ git clone https://github.com/kanemathers/dotdrop.git ~/Dropbox

2. Run dotdrop:

        $ ~/Dropbox/dotdrop/dotdrop

3. dotdrop should be run on startup to ensure your local symlinks keep in
   sync with your plugins:

        $ echo "[[ -f ~/Dropbox/dotdrop/dotdrop ]] && source ~/Dropbox/dotdrop/dotdrop" >> ~/.bash_profile

Configuration
-------------

Environment variables are used to configure dotdrop.

`DOTDROP_SLEEP` - default: "10" - How long to sleep before syncing plugins.

`DOTDROP_NOFIFY` - default: "no" - Enable notifications.
