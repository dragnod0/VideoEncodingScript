# About
These Bash scripts can convert multible files inside a single folder (not recursive) into another. It's grap the name from the source files and give the destitnation file the same name.
The scripts are testet on debian and Ubuntu based Linux Distros.


# Requiments
#### FFMPEG
##### Ubuntu & Debian based Distros:
```
sudo apt update
sudo apt install ffmpeg
```

#### HanBrakeCli
##### Ubuntu & Debian based Distros
```
sudo add-apt-repository -y ppa:stebbins/handbrake-releases
sudo apt update
sudo apt install handbrake-cli
```
If you missing the ```add-apt-repository``` in Debian [see here](https://computingforgeeks.com/how-to-install-add-apt-repository-on-debian-ubuntu/) 

# Installation
1. Download or Copy the scripts into the /bin dir for system wide use.
2. Make the scripts executable with ```sudo chmod +x /bin/[Filename]```


# Syntax
> [scriptname] [source  container] [destination container] [sorce directory] [destination directory] 

An example:
> ffmpeg-batch mkv mp4 /home/user/Movies /home/Movies/optimized
In this example the Script encode all mkv Videos into mp4 files. All other containers will be ignored. 

***Important: Don't use slash "/" at the end of the path. Otherwise the script does't work!***
***This is WRONG: /home/user/Movies/*** 


# Features 
#### ffmpeg-batch
- CPU based encoding
- adds chapter from the Source
- remove black bars
- assume the forced subtitle
- Checks whether the file already exists in the target folder
- easy change the ffmpeg encoding options

#### ffmpeg-batch-gpu
- GPU based encoding with vaapi
- adds chapter from the Source
- assume the forced subtitle
- Checks whether the file already exists in the target folder
- easy change the ffmpeg ecoding options
- ***remove black bars is not possible with GPU encoding!***

#### hanbrake-batch
- CPU based encoding
- adds chapter from the Source
- remove black bars
- assume the forced subtitle
- Checks whether the file already exists in the target folder
- easy change the HadBrakeCli encoding options
- ***The script is costamized for german audio and subtitle tracks. You must change it with the ISO 639-2 code (e.g. fre, eng, spa, dut, et cetera)

# FFMPEG vs. HandBrakeCli - The differences
### FFMPEG
- you can relative easy add more advanced options
- supports GPU encoding 
- it's relativ hard to add extras (subtitles, auto crop black bars, chapter, ...) 
- can copy Video track if you just want to convert only the audio track

### HandBrakeCLI 
- makes the most features automatic 
- has no GPU encoding Support 
- has no support for more advanced options (thay are not documentet for CLI) 


# FFMPEG or HandBrakeCli?
For most tasks and if you don't need support for GPU encoding HandBrakeCLI is the best option. 
Only you will encode with your graphic card or need advanzed options you must use FFMPEG. 
