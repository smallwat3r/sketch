```
       __       __      __
  ___ / /_____ / /_____/ /
 (_-</  '_/ -_) __/ __/ _ \'
/___/_/\_\__/\__/\__/_//_/
```

# Sketch

I always keep a blank file open in a corner of my screen in case I need to quickly note or copy something for later. But I spend most of my time in my terminal and I've decided to build a simple bash script that will help me save time.

Sketch is a small productivity script to rapidly generate and access draft files from a unique folder directly from the terminal.  

![sketch](https://i.imgur.com/Z3TX3Of.gif)  

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

sketch -l<number> open archived saved files. Example: -l1 will
                  open the last sketch file saved, -l2 will open
                  the previous one, etc.

Optional Arguments
------------------------------------------------------------

-h, --help        show this help message and exit.
-pu, --purge      purge all the files archived in set-up temp dir.
-v, --version     sketch version.
```

---

Sketch is archiving the saved draft files under a default dir at  `$HOME/.local/share/sketch_dir` or `$XDG_DATA_HOME/sketch_dir` (if `sketch_dir` not specified in `.sketchconfig`), all the files are named as `<incremental_integer>.sketch`

