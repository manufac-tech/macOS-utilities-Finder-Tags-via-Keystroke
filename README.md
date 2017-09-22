# macOS-Finder-Tags-via-Keystroke  
Use keyboard shortcuts to assign tags to items in macOS Finder.

## Overview  
Portland's own [James Berry](https://github.com/jdberry) made a very useful command line tool (_[tag](https://github.com/jdberry/tag)_) that can, among other things, add and remove tags to Finder items.  

It can add tags:  
`tag -a FrikkinTag`  

It can remove tags:  
`tag -r FrikkinTag`

More in the _tag_ [README](https://github.com/jdberry/tag).  

The example Automator workflows I have included here are one way to trigger _tag_ to act on the selected finder items via keyboard shortcut.  

(This functionality is probably available using LaunchBar, Alfred, Keyboard Maestro, etc., but I wanted to assign tags via keyboard w/o needing any other apps running.)  


Open the workflows in Automator to see how simple they are - I just:  
1. Used the _tag_ command in a tiny Bash script  

    for f in "$@"  
    do  
    /usr/local/bin/tag -a –flag "$f"  
    done  

2. Wrapped it in an Automator workflow  
3. Saved it as a macOS Service  
4. Assigned a keyboard shortcut to the Service.  

Note: Services can be assigned a keyboard shortcut in _System Preferences -> Keyboard -> Shortcuts -> Services._  


## Setting up _tag_ using homebrew in macOS terminal  
Requirements (from the [README.md](https://github.com/jdberry/tag/blob/master/README.md))  
1. "10.9 Mavericks and above"  

2. "You must have Xcode or the Command Line Tools installed to build/install."

Installation of _tag_  
1. Install [Homebrew](https://github.com/Homebrew/brew/) on your Mac. 
	I might have used [this](https://www.moncefbelyamani.com/how-to-install-xcode-homebrew-git-rvm-ruby-on-mac/) tutorial.  

2. Install the _tag_ package via the command line.  
`brew install tag`  
