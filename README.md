# macOS-Finder-Tags-via-Keystroke  
Use keyboard shortcuts to assign tags to items in macOS Finder.

### Made possible by the "tags" command    
Portland's own [James Berry](https://github.com/jdberry) made a very useful command line tool (_[tag](https://github.com/jdberry/tag)_) that can, among other things, add/remove tags to/from Finder items.  
- It can add tags:  
	`tag -a FrikkinTag`  

- It can remove tags:  
	`tag -r FrikkinTag`

More in the _tag_ [README](https://github.com/jdberry/tag).  

### Automator workflow (saved as a Service)
The example Automator workflows I have included here are one way to trigger _tag_ to act on the selected finder items via keyboard shortcut. (This functionality is probably available using LaunchBar, Alfred, Keyboard Maestro, etc., but I wanted to assign tags via keyboard w/o needing any other apps running.)  


Open the workflows in Automator to see how simple they are:  
1. The _tag_ command is used a tiny Bash script. Note: The Automator action requires including the path to the command.

    for f in "$@"  
    do  
    /usr/local/bin/tag -a –flag "$f"  
    done  

2. The Bash script is wrapped in an Automator workflow  
3. The workflow is saved as a macOS Service  
4. A keyboard shortcut is assigned to the Service. 

Note: Services can be assigned a keyboard shortcut in _System Preferences -> Keyboard -> Shortcuts -> Services._  


### Setting up _tag_ using homebrew in macOS terminal  
Requirements (from the [README.md](https://github.com/jdberry/tag/blob/master/README.md))  
1. 10.9 Mavericks and above  
2. You must have Xcode or the Command Line Tools installed to build/install.  

Installation of _tag_  
1. Install [Homebrew](https://github.com/Homebrew/brew/) on your Mac.  
2. Install the _tag_ package via the command line.  
`brew install tag`  
