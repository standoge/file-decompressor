# Files decompressor 
I don't have any graphic tool like unzip or unrar on my computer, so when I want to decompress a file I've to use `unzip` or `unrar` tool from terminal, and I'm good with that I like it, but both has different argument and parameters so I never remember which is for which, and don't mention arguments needed to decompress `tar.gz` files, so I decide to create a script that combine the three commands to be easy to use.

## Requirements :mag_right:
Is necessary that you have mentioned tools instaled on your computer, `unzip`,`unrar` and `xz` tools; `tar` actually comes instaled on Mac and Linux. First two tools can be downloaded easily using `requirments.sh` file executing it as follow:

```Bash
./requirments.sh 
```
For distros like Arch or Debian the script will detect automatically the os to use the correct package manager. Only for Mac you must to use `-mac` argument in script call.

**Note**
:		Remember to give permitions to `requirements.sh` before to try to execute.

## How to use :ringed_planet:
You can run the script on your terminal each time do you need or the option that I recomend is save the script as alias on your bash/zsh rc file as follow:

```Bash
alias dpress=/~/path/file-decompresser/dpress.sh
```

then, you can use it only writting the alias and giving the file on your terminal:
```Bash
dpress <flag> <file.extension> <...>  
```
The script will detect file extension and use the tool with their arguments to decompress in current directory. To change default behavior, use one of these arguments/flags:

| Argument | Description                                                                                 |
|----------|---------------------------------------------------------------------------------------------|
| `-l`       | List files in compressed file before to decompress                                          |
| `-d`       | Giving a third argument you can select the directory where files goes when are decompressed |
| `-c`       | Create a compressed file, can be `zip`, `rar`,`tar.gz` or `tar.xz` file|
| `-m`       | Decompress an array of files. For this you've to pass an `.txt` file with file names. One per line|
| none     | Default behavior, just decompress files on current directory                                |

**Note**
:		Default behavior is always remove compressed file after decompress it, take care of that.

## Limitations :construction:
1) For files with names separated with spaces, you must rename that file to `trim` or `strip` its name , otherwise you will get an [error](https://stackoverflow.com/questions/30999227/how-to-solve-unzip-cannot-find-or-open-error-in-linux-os).
2) For files with `xz` extension you only must compress and decompress a dir with many files, doesn't work if you try to do with a single file.
3) You must have installed `zip` and `rar` tool before to try execute `requirements.sh`(where you install `unzip` etc) on `Arch` distrution only. This 'cause isn't possible install they from `pacman` repository.

---
Enjoy :bamboo:
