## .files and macOS setup

Contains macOS configuration files for various apps and instructions for setting up a new Mac.

### Setup

1. Update everything that is available in the App Store
2. Install Xcode
3. Install [Homebrew](https://brew.sh)

### Install Homebrew packages

```bash
$ brew tap caskroom/cask
$ brew cask install dropbox google-chrome spotify slack firefox notion toggl
$ brew cask install docker tower iterm2 macvim visual-studio-code atom appcode android-studio cyberduck simsim
$ brew cask install mysqlworkbench psequel sequel-pro postgresql sqlitebrowser
$ brew cask install alfred fluid spectacle flycut appcleaner caffeine marta flux keepassxc omnidisksweeper
$ brew cask install google-photos-backup-and-sync adobe-acrobat-reader handbrake vlc libreoffice
$ brew install Caskroom/versions/google-chrome-canary
$ brew install rbenv git carthage swiftformat yarn autojump lnav watchman tree ncdu
```

### Install others

These aren't installed through Homebrew

* [nvm](https://github.com/creationix/nvm#git-install)
* [Bash it](https://github.com/Bash-it/bash-it)
* [Powerline fonts](https://github.com/powerline/fonts)
* [FruitJuice](https://itunes.apple.com/us/app/fruitjuice-battery-health/id671736912?mt=12)
* Google Drive File Stream
* Lastpass
* [Todoist](https://apps.apple.com/ca/app/todoist-organize-your-life/id585829637?mt=12&ign-mpt=uo%3D4)
* [Tomato One](https://apps.apple.com/us/app/tomato-one-free-focus-timer/id907364780?mt=12)
* [Pocket](https://apps.apple.com/app/pocket/id568494494?ls=1&mt=12)
* [Monosnap](https://apps.apple.com/us/app/monosnap-screenshot-editor/id540348655?mt=12)
* [Logitech Options](http://support.logitech.com/en_us/software/options)
* [Paragon NTFS](https://www.paragon-software.com/ufsdhome/ntfs-mac/)

### NPM

1. Install the latest Node version.

    ```bash
    npm intall <version>
    ```

2. Install global packages.

    ```bash
    npm install -g machine-share
    ```

### Ruby

1. Install the latest Ruby version.

    ```bash
    # List all available versions
    rbenv install -l

    # Install 
    rbenv install <version>
    ```
2. Set it as the global version. 

   ```bash
   rbenv global <version>
   ```

3. Install Bundler. 

   ```bash
   gem install bundler
   ```

### macOS

1. Set to always show hidden files

   ```bash
   defaults write -g AppleShowAllFiles -bool true
   ```
   
   Restart Finder.

### Bash-it

1. Clone this repo to a local dir (e.g. `~/.files`). Make sure to use `--recursive` when cloning or run `git submodules update --init --recursive` after cloning.
2. Symlink `dotfiles/.bash_profile` to `~/.bash_profile`
3. Restart Terminal or iTerm2
4. Enable plugins, aliases, and completions

   ```bash
   $ bash-it enable plugin git autojump edit-mode-vi history
   $ bash-it enable alias git
   $ bash-it enable completion npm git docker docker-compose docker-machine bundler
   ```

### Git

```bash
$ git config --global user.name "Shiki"
$ git config --global user.email "jayson@basanes.net"
```

### Atom

Atom settings are synchronized using the [sync-settings](https://github.com/atom-community/sync-settings) package. It saves the settings in Gist. The gist is private and the location is stored in my LastPass.

1. Install the [sync-settings](https://github.com/atom-community/sync-settings) package manually in Atom.
2. Configure sync-settings to fill in the gist id and Github access token
3. Run the _Sync Settings: Restore_ command in Atom

### MacVIM

1. Symlink `.vim` 

   ```bash
   $ ln -s ~/.files/vim/vim.symlink ~/.vim
   ```
2. Install [Vundle](https://github.com/VundleVim/Vundle.vim). Follow all instructions until the `:PluginInstall` has been executed
3. Symlink `.vimrc`
   ```bash
   $ rm ~/.vimrc
   $ ln -s ~/.files/vim/vimrc.symlink ~/.vimrc
   ```
4. In MacVIM, run `:PluginInstall` to install all plugins. This instructs the [Vundle](https://github.com/VundleVim/Vundle.vim) package to install all the other packages managed by it.
5. The VIM config uses DejaVu Sans Mono for Powerline. For VIM to use this font in the terminal, make sure to set this font as the default font in the Terminal or iTerm2.

### Xcode

1. Intall XVim plugin
2. For the custom XVim keybindings:
  1. Symlink `XVim.idekeybindings.symlink`
     ```bash
     $ ln -s ~/.files/xcode/KeyBindings/XVim.idekeybindings.symlink ~/Library/Developer/Xcode/UserData/KeyBindings/XVim.idekeybindings
     ```
  2. Enable the keybinding in XCode > Preferences > Key Bindings
4. Add the custom XCode color themes
  1. Symlink `dotfiles/xcode/FontAndColorThemes.symlink` to `~/Library/Developer/Xcode/UserData/FontAndColorThemes`
     ```bash
     $ ln -s ~/.files/xcode/FontAndColorThemes.symlink ~/Library/Developer/Xcode/UserData/FontAndColorThemes
     ```
  2. Choose a theme in XCode > Preferences > Fonts & Colors
  3. Manually change the Font for the theme

Xcode themes were taken from [hdoria/xcode-themes](https://github.com/hdoria/xcode-themes).

### Android Studio 

Follow the IntelliJ [Share settings through a settings repository](https://www.jetbrains.com/help/idea/sharing-your-ide-settings.html#settings-repository) instructions to synchronize the Android Studio settings. Use the `android-studio-settings` Github repo. 

### AppCode

Follow the IntelliJ [Share settings through a settings repository](https://www.jetbrains.com/help/idea/sharing-your-ide-settings.html#settings-repository) instructions to synchronize the AppCode settings. Use the `appcode-settings` Github repo. 

### Alfred

Follow the instructions in [Sync your Alfred settings between Macs](https://www.alfredapp.com/help/advanced/sync/) to synchronize the settings using Dropbox. 

These workflows should be automatically installed:

* [Convert](https://github.com/deanishe/alfred-convert)
* [Encode/Decode](https://github.com/willfarrell/alfred-encode-decode-workflow)
* [DevDocs](https://github.com/yannickglt/alfred-devdocs)
* [Faker](https://github.com/zenorocha/alfred-workflows)
* [Github](https://github.com/gharlan/alfred-github-workflow)
* [IP Address](https://github.com/zenorocha/alfred-workflows)
* [Kill Process](https://github.com/zenorocha/alfred-workflows)
* [Pomodoro](https://github.com/ecbrodie/pomodoro-alfred)
* [Spotify Mini Player](http://alfred-spotify-mini-player.com/)
* [Stack Overflow](https://github.com/zenorocha/alfred-workflows)
* [Terminal-Finder](https://github.com/LeEnno/alfred-terminalfinder)
* [TimeZones](https://github.com/jaroslawhartman/TimeZones-Alfred)
* [UUID Generator](http://www.packal.org/workflow/uuid-generator-0)

### Chrome

Install extensions

* Lastpass
* Adblock
* Vimium
* Save to Pocket

### iTerm2

Install themes from http://iterm2colorschemes.com/

* Flatland
* Dracula
* Hardcore
* Japanesque
* Space Grey Eighties Dull
