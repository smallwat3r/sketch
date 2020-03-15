```
       __       __      __
  ___ / /_____ / /_____/ /
 (_-</  '_/ -_) __/ __/ _ \'
/___/_/\_\__/\__/\__/_//_/
```

# Sketch

I always kept a blank file open in a corner of my screen in case I need to quickly note or copy something for later. I created a simple bash script that helps me save time to create / reopen draft notes.

Sketch is a small productivity script to rapidly generate and access draft files from a unique folder directly from the terminal.

Sketch works with all text editor that can be opened from a terminal command (`vim`, `macvim`, `nano`, `subl` etc).

![sketch](https://i.imgur.com/GyXRYVT.gif)  

## Set up
Clone this repository and run the following commands.  
```sh
git clone https://github.com/smallwat3r/sketch.git
cd sketch
make install
```

or  
```sh
git clone https://github.com/smallwat3r/sketch.git
cd sketch
cp sketch /usr/local/bin/sketch && chmod 755 /usr/local/bin/sketch
```

or (without cloning)  
```sh
sudo wget https://raw.githubusercontent.com/smallwat3r/sketch/master/sketch \
    -P /usr/local/bin && sudo chmod 755 /usr/local/bin/sketch
```

You can now run sketch by typing `sketch` in your terminal.  

## Usage

```
sketch            automatically open a new draft file from the 
                  sketch directory.

sketch -r<number> open archived saved file. Example:
                  sketch -r1 will reopen the last sketch file saved
                  sketch -r2 will reopen the previous one
                  etc...

Other Arguments
------------------------------------------------------------

-h, --help        show this help message and exit.
-pu, --purge      purge all the files archived in set-up temp dir.
-v, --version     sketch version.
```

## Customization and info

#### Archived files

Each time a sketch file is created and saved, it is archived under a specific directory.
```
# Sketch file directory location.
# if exists:
$XDG_DATA_HOME/sketch_dir
# else under:
$HOME/.local/share/sketch_dir 
```
Archived files naming convention: `<integer>.sketch`.  
So you can reopen these files using `-p<integer>`.  
To delete all these files use `-pu` or `--purge`.  

#### .sketchconfig file

In `.sketchconfig` you can enter your favourite text editor (ex: `vim`, `nano`, `subl` ...).
```
# .sketchconfig location check by priority order.
$XDG_CONFIG_HOME/.sketchconfig
$HOME/.config/.sketchconfig
$HOME/.sketchconfig
```

* editor: If not specified, sketch check for `$EDITOR` if your env variables. If it still does not exists,
then it defaults to vim.  
* sketch_dir: You can specify a custom directory from where your sketch files will be archived.  

```
# .sketchconfig example file.

# Your favourite editor to use Sketch (vim, nvim, subl, emacs, nano etc)
editor=vim

# Archives folder.
sketch_dir=~/.sketch_dir
```
