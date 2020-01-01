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

![sketch](https://i.imgur.com/Wu7797l.gif)  

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
cp bin/sketch /usr/local/bin/sketch && chmod 755 /usr/local/bin/sketch
```

or (without cloning)  
```sh
sudo wget https://raw.githubusercontent.com/smallwat3r/sketch/master/bin/sketch -P /usr/local/bin && sudo chmod 755 /usr/local/bin/sketch
```


You can now run sketch by typing `sketch` in your terminal.  

In `~/.sketchconfig` you can enter your favourite text editor (ex: `vim`, `nano`, `subl` ...), note that `vim` is set-up as default.  
You can also chose the folder location from where your sketch files are archived.  

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

---

Sketch is archiving the saved draft files under a default dir at  `$HOME/.local/share/sketch_dir` or `$XDG_DATA_HOME/sketch_dir` (if `sketch_dir` not specified in `.sketchconfig`), all the files are named as `<incremental_integer>.sketch`

