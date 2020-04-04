```
       __       __      __
  ___ / /_____ / /_____/ /
 (_-</  '_/ -_) __/ __/ _ \'
/___/_/\_\__/\__/\__/_//_/
```

# Sketch

I always kept a blank file open in a corner of my screen in case I need to quickly note or copy something for later. This simple bash script helps me save time to create / reopen my draft notes.

Sketch is a small productivity tool to generate and access / store draft files directly from the terminal.

Sketch works with all text editor that can be triggered from a terminal command (vim, nvim, macvim, nano, subl etc...).

![sketch](https://i.imgur.com/uHwSDXJ.gif)  

## Set up
Clone this repository and run the following commands (might need to run with sudo).  

```sh
git clone https://github.com/smallwat3r/sketch.git \
  && cd sketch \
  && make install
```

or  
```sh
git clone https://github.com/smallwat3r/sketch.git \
  && cd sketch \
  && cp sketch /usr/local/bin/sketch && chmod 755 /usr/local/bin/sketch
```

or (without cloning)  
```sh
wget https://raw.githubusercontent.com/smallwat3r/sketch/master/sketch \
    -P /usr/local/bin && chmod 755 /usr/local/bin/sketch
```

You can now run sketch by typing `sketch` in your terminal.  

## Usage

```
sketch is a small productivity tool to rapidly generate and
access draft files from the terminal.

sketch            automatically creates and open a new draft
                  file from the temporary directory.

sketch <number>   open archived saved file. Ex:
                  sketch 1 will reopen the last saved file.
                  sketch 2 will reopen the previous one
                  etc...

sketch ls         list all archived files.

sketch purge      delete all the archived files.

Other Arguments
------------------------------------------------------------
-h, --help        show this help message and exit.
-v, --version     script version.
```

## Customization and info

#### Archived files

Each time a sketch file is created and saved, it is archived under a specific directory.
```
# Sketch file directory location.
# if exists:
$XDG_DATA_HOME/sketch_archives
# else under:
$HOME/.local/share/sketch_archives 
```
Archived files naming convention: `<int>.sketch`.  
So you can reopen these files using `sketch <int>`.  
To delete all these files use `sketch -pu` or `sketch --purge`.  

#### .sketchrc file

In `.sketchrc` you can enter your favourite text editor (ex: `vim`, `nano`, `subl` ...).
```
# .sketchrc location check by priority order.
$XDG_CONFIG_HOME/.sketchrc
$HOME/.config/.sketchrc
$HOME/.sketchrc
```

* **SKETCH_EDITOR**: If not specified, sketch check for `$EDITOR` if your env variables. If it still does not exists,
then it defaults to vim.  
* **SKETCH_ARCHIVES**: You can specify a custom directory from where your sketch files will be archived.  

```
# .sketchrc example file.

# Your favourite editor to use Sketch (vim, nvim, subl, emacs, nano etc)
SKETCH_EDITOR=vim

# Archives folder.
SKETCH_ARCHIVES=~/.sketch_archives
```
