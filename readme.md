```
       __       __      __
  ___ / /_____ / /_____/ /
 (_-</  '_/ -_) __/ __/ _ \'
/___/_/\_\__/\__/\__/_//_/
```

# Sketch

I always keep a blank file open in a corner of my window in case I need to quickly  note or copy something for later. But I spend most of my time in my  terminal and I've decided to build a simple bash script that will help  me save time.

Sketch is a small productivity script to rapidly generate and access draft files from a unique folder directly from the terminal.  

## Set up
Clone this repository and run the following commands.  
```sh
cp src/sketch .sketchconfig ~
chmod +x ~/sketch
```
A good thing is to alias Sketch to a shortcut to run it faster from the terminal .  I personaly use `s`.  You will need to close and reopen your terminal so the change can apply.  
```sh
# ~/.zshrc or ~/.bashrc
alias s="~/./sketch"
```
## Usage

In `~/.sketchconfig` you can enter your favourite text editor (ex: `vim`, `nano` or `subl`), note that `vim` is set-up as default (`:q!` to exit if needed lol).  

**Let's suppose you aliased sketch to `s`**  

-  `s` automatically open a new draft file from the sketch directory.  
-  `s -h` or `s --help` to get help on how to use sketch. 
-  `s -l<number>` to re-open archived sketch files you saved. For example `-l1` will open the last sketch file you saved.` ``-l2` will open the previous, etc.  
-  `s -pu` or `s --purge` to purge all the draft files sketch created.  

 Sketch is archiving the saved draft files under a directory at  `~/.sketch.swp` , all the files are named as `<incremental_integer>.sketch`

